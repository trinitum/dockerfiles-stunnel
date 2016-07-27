# dweomer/stunnel [![Docker Stars](https://img.shields.io/docker/stars/dweomer/stunnel.svg?maxAge=2592000)]() [![Docker Pulls](https://img.shields.io/docker/pulls/dweomer/stunnel.svg?maxAge=2592000)]()

To secure an LDAP container named `directory`:

```
docker run -itd --name ldaps --link directory:ldap \ 
        -e STUNNEL_SERVICE=ldaps \
        -e STUNNEL_ACCEPT=636 \
        -e STUNNEL_CONNECT=ldap:389 \
        -p 636:636 \
#       -v /etc/ssl/private/server.key:/etc/stunnel/stunnel.key:ro \
#       -v /etc/ssl/private/server.crt:/etc/stunnel/stunnel.pem:ro \
    dweomer/stunnel
```
