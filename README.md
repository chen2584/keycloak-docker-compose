# keycloak-docker-compose
Study project.

### Initial Postgres Database
```
create database keycloak with encoding 'UTF8';
```

### Generate TLS (Self-signed certificate)
```
openssl req -newkey rsa:2048 -nodes -keyout keycloak-server.key.pem -x509 -days 3650 -out keycloak-server.crt.pem 
```