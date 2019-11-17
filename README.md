# Docker composer
To start dev env run:
```
docker-compose up -d
```

To stop run:
```
docker-compose down
```

### Setup /etc/hosts
Edit you `/etc/hosts` file in your machine like this:
```
127.0.0.1 api-dev.example.com dev.example.com
```

# Self Signed local certificate
To generate a local cert we use [mkcert](https://github.com/FiloSottile/mkcert).
Follow these steps to generate your local dev cert
```
mkcert "api-dev.example.com" "dev.example.com"
// Now we need to install the CA from mkcert in our machine/browser
mkcert --install
```
Copy generated certs `.pem` files to [nginx/certs](./nginx/certs)

Note that if later you want another subdomain you will have to generate
a new certificate with that new subdomain. This certificate is only valid for:
1. `dev.example.com`
2. `api-dev.example.com`
