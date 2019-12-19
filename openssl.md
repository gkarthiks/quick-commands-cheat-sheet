OpenSSL is a SSL Tool and is an open source implementation of the SSL protocol.

Command | Description
--|--
openssl s_client -showcerts -connect \<url\> | Displays all the certificates (including Intermediates) and certificate related details
openssl x509 -inform der -in certificate.cer -out certificate.pem | Converts a DER file (.crt .cer .der) to PEM
openssl x509 -outform der -in certificate.pem -out certificate.der | Converts a PEM file to DER
openssl pkcs12 -in keyStore.pfx -out keyStore.pem -nodes | Converts a PKCS#12 file (.pfx .p12) containing a private key and certificates to PEM
openssl pkcs12 -export -out certificate.pfx -inkey privateKey.key -in certificate.crt -certfile CACert.crt | Converts a PEM certificate file and a private key to PKCS#12 (.pfx .p12)
