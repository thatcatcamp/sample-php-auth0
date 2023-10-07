# Enabling Auth0 with PHP

## setup

The walkthrough on the site isn't accurate - ignore it and use this kickstart.

1) drop these files into /var/www/html on the server, running nginx (can use apache, but different config).  keep default html file
2) follow basic nginx/php set up here ->  https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-22-04
3) enable letsencrypt like there -> https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-22-04
4) test by loading the default page
5) if okay - delete the html
6) mv the .env sample file to .env - update the fields marked in comments
7) update the application in auth0 console - don't use localhost  :-|  use real server with https
8) update `/etc/nginx/sites-enabled/default` to include the buffer parameters in the main and php blocks (login will fail with a 502 otherwise)
9) `nginx -t` to test config
10) `systemctl restart nginx` - should be alive :D
