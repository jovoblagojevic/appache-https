# appache-https

# Creating Self-Signed SSL Certificate

sudo apt install openssl

openssl req -newkey rsa:4096 \
            -x509 \
            -sha256 \
            -days 3650 \
            -nodes \
            -out server.crt \
            -keyout server.key
            
# Enable SSL - Apache

Open Apache SSL configuration file: httpd.conf  
Uncomment: LoadModule ssl_module modules/mod_ssl.so  
Uncomment: LoadModule ssl_module modules/mod_ssl.so  
Uncomment: Include conf/extra/httpd-ssl.conf  
Add Line SSLCertificateFile     /usr/local/apache2/conf/server.crt  
Add line: SSLCertificateKeyFile  /usr/local/apache2/conf/server.key  
