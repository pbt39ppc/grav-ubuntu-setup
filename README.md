# grav-ubuntu-setup
Helps to prepare devserver

on the server console 
```ifconfig```
to see your ip address, connect to that with putty
get root rights
```sudo su -```

update and reboot
```apt update && apt upgrade -y && reboot```



```apt install mc htop nginx php-fpm php-mbstring php-gd php-curl php-xml php-zip```  
```cd /var/www/html; wget https://getgrav.org/download/skeletons/onepage-site/2.0.0 -O file.zip; unzip ./file.zip; rm ./file.zip; cd ./g*; mv ./{.,}* ..; cd ..; rm -rf ./grav*; mv ./index.nginx-debian.html ./index.nginx-debian.html.bak; chown -R www-data:www-data /var/www/html; ```

```cd ./we*; mv ./ng* /etc/nginx/sites-available/default```

```chmod +x /var/www/html/bin/gpm```
_____________________________________
change that file /etc/nginx/sites-available/default
 #listen 80;
to
  listen 80;

  root /home/USER/www/html;
to
  root /var/www/html;

 fastcgi_pass unix:/var/run/php5-fpm.sock;
to
 fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
_____________________________________


now you can access your grav by ip 

also you can install admin plugin (if not existed in your skeleton yet)
but first upgrade grav

su -s /bin/bash www-data
cd /var/www/html; 
bin/gpm self-upgrade
bin/gpm install admin
then access your site from the frontend and fill the form to create admin account.




If that was helpful for you, you can donate some
BTC: 16KwoeBwJaKrdQ7ujHinuaEsoEGDXsG8Hz
