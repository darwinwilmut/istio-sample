The certificates in this folder are generated by Let's encrypt.

How to generate these SSL Certificate ?

1. Create the azure linux vm with the region where your istio-ingress gateway ip exist.

For eg. If my istio-ingress gateway ip region is westus3 then your linux vm's ip must be in the westus3 region.

2. Install nginx and certbot in the linux vm.

3. Update the domain name in the server name field that is in the nginx configuration.

4. sudo nginx -t = To check the nginx conf file syntax

5. sudo nginx -s reload = To reload the nginx configuration

6. Now create the ssl certificate to the custom domain by using the following command.

sudo certbot --nginx -d yourdomain.com

7. save the contents of the privkey.pem fullchain.pem as a file

8. Now load these privkey.pem and fullchain.pem file to the kubernetes by creating the secret.Use the following command to create the secret.

kubectl create -n istio-system secret tls httpbin-credential --key=privkey.pem --cert=fullchain.pem

Note: You have to create the secret in the istio-system namespace
