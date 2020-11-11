# Transmission with SSL on Synology DSM
Access your transmission website with DSM cert on Synology NAS.

## What you need:
1. Install transmission from package center.
2. Root permission.

## Installation
```
# Create htpasswd file:
sudo sh -c "echo -n '${TRANSMISSION_LOGIN_USER}:' >> /etc/nginx/conf.d/.transmission.htpasswd"
sudo sh -c "openssl passwd -apr1 >> /etc/nginx/conf.d/.transmission.htpasswd"

# Install nginx config:
cp dsm.transmission.conf /etc/nginx/conf.d/
nginx -s reload
```

## New entrypoint will be:
```
https://DSM_LOGIN_DOMAIN:DSM_LOGIN_PORT/transmission/

ex:
https://kevinfang.synology.me:5000/transmission/
```

## Customization
Change location path if you want a different URL path.