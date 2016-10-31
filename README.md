xcarve-iris
===

Containerized versions of the [Easel driver](http://easel.inventables.com/downloads).

Tags
---
The tag represents the Easel driver version. The `*-rpi` tags are based on an ARM Raspbian image.

Usage
---
Plug in your X-Carve and run it like this:
```
$ docker run --privileged -p 1338:1338 rohan/xcarve-iris
```

The [Easel web app](http://easel.inventables.com/) will attempt to connect to the driver at
`localhost:1338`. If you are running the web app on the same machine as the container, it should
"just work". Otherwise you can use SSH port mapping:

```
$ ssh -L 1338:localhost:1338 your-xcarve-server
```
