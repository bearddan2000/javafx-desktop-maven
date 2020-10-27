# javafx-desktop

## Description
This is a POC project to demonstrate a
javafx application running inside a docker container.

## Tech stack
- jdk 11
- javafx 11
- maven 3.4
- docker-cli
- docker-compose
- bash
- xhost

## Docker stack
- ubuntu:latest
- openjdk:11-jdk

## To run
```xhost +localhost && sudo ./install.sh -u```

## To stop (optional)
```xhost && sudo ./install.sh -d```

## Credits
https://stackoverflow.com/questions/52144931/how-to-add-javafx-runtime-to-eclipse-in-java-11
https://www.mymiller.name/wordpress/docker/javafx-maven-docker-image-openjfx/
