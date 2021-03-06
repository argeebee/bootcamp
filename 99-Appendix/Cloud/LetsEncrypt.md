# Let's Encrypt

[Let's Encrypt](https://letsencrypt.org/)

Let's Encrypt provides free and automatic domain validation (DV) certs. [Certbot](https://certbot.eff.org/) is popular utility for installing and maintaining Let's Encrypt certificates.

## Install Certbot
```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-apache
```

## Install the Certificate
Run Certbot with the Apache option and follow the prompts.
```
certbot --apache
```

## Certificate Renewal
Use a crontab to auto renew your cert.
```
crontab -e
```

Add the following line. This will attempt a certificate renewal once a month at 10pm. The certificate will only only renew if it is close to expiry. Replace 15 with today's date minus one, this however, should be no higher than 27 to account for the shortest possible month.
```
0 22 15 * * certbot renew
```

## Additional Resources
[Install Certbot on Ubuntu](https://certbot.eff.org/#ubuntutrusty-apache)
