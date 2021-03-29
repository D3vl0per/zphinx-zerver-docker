# zphinx-zerver
https://github.com/stef/zphinx-zerver

## Images
Docker registry(Signed): `d3vm/zphinx-zerver:latest`
GitHub registry: `docker.pkg.github.com/d3vl0per/zphinx-zerver-docker/zphinx:latest`

## SSL generation

1. Generate own private key: `openssl ecparam -genkey -out domain.key -name secp384r1`
2. Generate CSR: `openssl req -new -sha256 -key domain.key -subj "/CN=example.com" > domain.csr`
3. Use let's encrypt
4. Generate DER file from cert: `openssl x509 -outform der -in certificate.crt -out certificate.der`

