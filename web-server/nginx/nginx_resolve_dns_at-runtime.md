resolver 8.8.8.8 valid=5s;

map "" $amado_dev_server {
   default      dev.example.com;
}

map "" $amado_qa_server {
   default      qa.example.com;
}

map "" $amado_uat_server {
   default      uat.example.com;
}

server {
    
    listen 80;
    listen [::]:80;

    server_name proxy.example.com;
    server_tokens off;
    
    location / {
        proxy_pass         https://$amado_dev_server;
        mirror              /mirror;
        mirror              /mirror2;
        # proxy_redirect     off;
        proxy_pass_request_body on;
        proxy_set_header   Host $amado_dev_server;
    }

    location = /mirror {
        internal;
        proxy_pass   https://$amado_qa_server$request_uri;
        proxy_pass_request_body on;
        proxy_set_header   Host $amado_qa_server;
    }

    location = /mirror2 {
        internal;
        proxy_pass   https://$amado_uat_server$request_uri;
        proxy_pass_request_body on;
        proxy_set_header   Host $amado_uat_server;
    }

}