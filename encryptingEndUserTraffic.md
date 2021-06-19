![image](https://user-images.githubusercontent.com/528170/122650503-38de1280-d0e8-11eb-81db-d10f5bf356e1.png)



Create a Kubernetes secret with TLS credentials. 

1. Create the self-signed root certificate that will be used to sign the TLS certificate for ingress gateway: 
```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -subj '/O=boutiquestore Inc./CN=boutiquestore.com' -keyout root.key -out root.crt
```

2. Generate a private key and certificate signing request (CSR). It will be signed by the root CA and used for the TLS handshake:
```
openssl req -out server.csr -newkey rsa:2048 -nodes -keyout server.key -subj "/CN=marketplace.boutiquestore.com/O=boutique store"
```
3. Sign the CSR using the root CA from the above step. to create a kubernetes secret that the Istio ingress gateway can use
```
openssl x509 -req -days 365 -CA root.crt -CAkey root.key -set_serial 0 -in server.csr -out server.crt
```
4. Kubernetes secret using the server private key and public key 
```
kubectl -n istio-system create secret tls online-boutique-tls-credential --key server.key --cert=server.crt
```

Configure the TLS gateway resource
