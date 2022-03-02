# raspberry-setup

# Description
This repository contains configuration files for home assitant and nginx. This setup is dependent on [ha-support-service](https://github.com/nerijusdu/ha-support-service).

# Setup
- Clone [ha-support-service](https://github.com/nerijusdu/ha-support-service) to `~/projects/ha-support-service`
- Setup home assistant to `~/projects/home-assistant` directory
  - Copy files from this repositories `home-assistant` directory to `~/projects/home-assistant`
  - Run `docker-compose up -d`
- Copy files from this repositories `nginx` directory to `~/projects/nginx`
  - Replace `TODO-YOUR-PUBLIC-DOMAIN` with your domain (e.g. example.org)
  - Comment out ssl server and redirection to https in `nginx.conf`
  - Run `docker-compose up -d`
  - Run `docker-compose run --rm  certbot certonly --webroot --webroot-path /var/www/certbot/ -d example.org`
  - Uncomment everything from `nginx.conf`
  - Run `docker-compose restart`
