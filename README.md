# docker-wordpress

It is part of a [conjuction or repositories](https://github.com/search?q=user%3Admartingarcia+docker) that contain dockerised environments for small applications.

In this case, it contains a self-efficient *wordpress* setup.

## How to use it

```
cp .env.example .env
docker compose up -d
```

And browse into `http://localhost:8000

## Plugins

Well, you want to add plugins right?

then you need to add them into the plugins directory, but to make it easier to locate, I suggest to create a symlink to that directory:

```
ln -s wp/wp-content/plugins/ ./plugin
```

then, download and unzip all plugin files inside, and, _voilà_, you have them in your plugin tab inside of the administration page.

https://wordpress.org/plugins/ here you can obtain your plugins

## Traefik integration`

It also contains a Traefik integration, that interact with this reverse proxy, routing request to the wordpress container in case it matches the specified domain

## .env setup

It contains a basic set of variables like:

- Database credentials
- Docker image versions
- http host that uses Traefik to match requests

Please take a look on that and :warning: create your own credentials :warning: in case you want to expose it to the public.

## Docker Traefik

If you want to use this Traefik integration, [take a look at this repository](https://github.com/dmartingarcia/docker-traefik)
