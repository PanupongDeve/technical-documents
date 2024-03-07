
check ssl from url

openssl s_client -debug -connect <hostname>:<ssl_port>


get server cert from url

echo | openssl s_client -servername <hostname> -connect <hostname>:<ssl_port> | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > <hostname>.crt

check cert file

openssl x509 -in <cert_file> -text -noout
