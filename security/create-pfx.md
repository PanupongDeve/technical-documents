openssl pkcs12 -legacy -export -out <file_name>.pfx -inkey <private_key>.key -in <public_cert_chain>.cert -passin pass:<password> -passout pass:<password> -password pass:<password>