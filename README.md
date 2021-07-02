## Passwords file generation

```
$> htpasswd -c -b htpasswd/localhost admin admin
```

Passwords file was created on a ubuntu20.04 machine using "apache2-utils" version "2.4.41-4ubuntu3.3"

Passwords file is located in [htpasswd/localhost](htpasswd/localhost)

Default login is "admin/admin"


## How to reproduce the problem

```
$> git clone https://github.com/pescobar/jwilder-nginx-proxy-auth-tests.git
$> cd jwilder-nginx-proxy-auth-tests
$> docker-compose up
```

Now open [http://localhost](http://localhost) in your local brower and try to login as admin/admin


## How to check the running nginx config

Once the containers are running:

```
$> docker exec -ti ngix-basic-auth-tests_nginx_1 cat /etc/nginx/conf.d/default.conf
$> docker exec -ti ngix-basic-auth-tests_nginx_1 cat /etc/nginx/htpasswd/localhost
```

