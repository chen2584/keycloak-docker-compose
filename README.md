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

### Generate JWT Admin Token for Rest API
```
curl --location --request POST 'https://localhost:8443/realms/master/protocol/openid-connect/token' \
--header 'Authorization: Basic YWRtaW4tY2xpOktwV3dpbXJsMXFpSzN2cjA3WHZwN2NjYVRrWjF2SXl1' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'username=admin' \
--data-urlencode 'password=admin'
```