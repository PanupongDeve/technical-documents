## setup cert 
https://certbot.eff.org/instructions?ws=other&os=ubuntufocal

1. sudo apt-get remove certbot 
2. sudo snap install --classic certbot
3. sudo ln -s /snap/bin/certbot /usr/bin/certbot
4. sudo certbot certonly --standalone
5. cert should be store at /et/lensencrtypt
