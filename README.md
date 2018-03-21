# drupal 7 docker starter

## Prerequirments

- docker

- docker-compose

## Backstory

I'm making a webstie for my local assembly and I didn't want to install all the dependencies on my host, so I created this tiny project.

This project is based and inspired by [this repo](https://github.com/brunogoossens/Docker-Drupal8).

## Instructions

- Clone this repo and cd into it

``` bash
git clone https://github.com/benceHornyak/drupal7-docker-starter.git
cd drupal7-docker-starter/
```

- Download Drupal 7.57 into web/app and fire up docker-compose

``` bash
git clone -b "7.57" --single-branch https://github.com/drupal/drupal.git web/app
docker-compose up # -d if you don't want to see the logs
```

## Crditentials

During drupal installation here are the creditentials:

`Database name: drupal7`

`Database username: root`

`Database password: root`

Open the advanced options and:

`Database host: mysql`

`Database port: 3306`

From now on the rest is a regular installation.

If you want to use git for your drupal site make sure to remove `web/app` form the `.gitignore` file or just delete `.gitignore`.

And there you have it. You have your own local drupal 7 ready to mess around!

## Note

This is only for local development! I don't suggest it for production.