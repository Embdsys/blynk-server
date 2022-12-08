# Unofficial Blynk Server Docker Image for ARMv7

[![](https://images.microbadger.com/badges/image/maxbanton/blynk-server.svg)](http://microbadger.com/images/maxbanton/blynk-server) 
[![](https://images.microbadger.com/badges/version/maxbanton/blynk-server.svg)](http://microbadger.com/images/maxbanton/blynk-server)

GET LEGACY BLYNK ANDROID APT HERE: https://www.apkmirror.com/apk/blynk-inc/blynk-legacy/blynk-legacy-2-27-34-release/blynk-legacy-2-27-34-android-apk-download/download/?key=b38b3641ebb4081b5302878063245c2d6b620792&forcebaseapk=true

Runs your own [Blynk Server](https://github.com/blynkkk/blynk-server) in a Docker on ARMv7 container instead of relying on Blynk's public server.

[Blynk](http://www.blynk.cc) is the "first drag-n-drop IoT app builder for Arduino, Raspberry Pi, ESP8266, SparkFun boards, and others." Super fun.

## How To Use It

Easy peasy:

```sh
docker run maxbanton/blynk-server:latest
```

To forward IP ports from the host to the container, do this:

```sh
docker run -p 8080:8080 -p 8441:8441 -p 9443:9443 maxbanton/blynk-server:latest
```

To persist data, mount a directory into the container:

```sh
docker run -v $(PWD):/data maxbanton/blynk-server:latest
```

To include your own server.properties file, mount it into /config/server.properties

```sh
docker run -v $(PWD)/server.properties:/config/server.properties maxbanton/blynk-server:latest
```

Or you can use a data volume in another container (check out different data volume techniques [here](https://docs.docker.com/engine/tutorials/dockervolumes/)).

Based on [mpherg's](https://github.com/mpherg/blynk-server) work
