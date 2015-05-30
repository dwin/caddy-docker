# caddy-docker

A [Docker](http://docker.com) image for [Caddy](http://caddyserver.com).

[![](https://badge.imagelayers.io/abiosoft/caddy:0.7.0.svg)](https://imagelayers.io/?images=abiosoft/caddy:0.7.0 'Get your own badge on imagelayers.io')

## Getting Started

### Serve current directory

```
$ docker run -d -v `pwd`:/srv -p 2015:2015 abiosoft/caddy
```

Point your browser to `http://127.0.0.1:2015`.

### Using git sources

Caddy can serve sites from git repository using [git](https://caddyserver.com/docs/git) middleware.

##### Create Caddyfile

Replace `github.com/abiosoft/webtest` with your repository.

```
$ prinf "0.0.0.0\ngit github.com/abiosoft/webtest" > Caddyfile
```

##### Run the image

```
$ docker run -d -v `pwd`/Caddyfile:/etc/Caddyfile -p 2015:2015 abiosoft/caddy
```
Point your browser to `http://127.0.0.1:2015`.

## Usage

#### Default Caddyfile

The image contains a default Caddyfile.

```
0.0.0.0
browse
```

#### Paths in container

Caddyfile: `/etc/Caddyfile`

Sites root: `/srv`

#### Using local Caddyfile and sites root

Replace `/path/to/Caddyfile` and `/path/to/sites/root` accordingly.

```
$ docker run -d -v /path/to/sites/root:/srv -v path/to/Caddyfile:/etc/Caddyfile -p 2015:2015 abiosoft/caddy
```