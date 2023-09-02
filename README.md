# 2048 Dockerized

2048 Web Game Dockerized. Based on [gabrielecirulli/2048](https://github.com/gabrielecirulli/2048).

## Images

The available images are below. This images support `linux/amd64` and `linux/arm64` architecture only.

|     Registry     |       Tags       | Web Server |
| :---------------: | :--------------: | :--------: |
| riyangarma33/2048 | latest, lighttpd |  lighttpd  |
| riyangarma33/2048 |      nginx      |   nginx   |

## Run in Docker

There are two ways to run this image.

### Docker Run

* Pull the image.

  ```bash
  docker pull riyangarma33/2048:<tag>
  ```
* Run the image.

  ```bash
  docker run -t -p <your host port>:80 --name 2048 riyangarma33/2048:<tag>
  ```

### Docker Compose

* Create directory and docker-compose.yml.

  ```bash
  ~$ mkdir dockerized_2048 && cd dockerized_2048
  ~/dockerized_2048$ touch docker-compose.yml
  ```
* Configure docker-compose.yml.

  ```yaml
  version: '3.8'

  services:
    "2048":
      image: riyangarma33/2048:latest
      container_name: dockerized_2048
      restart: unless-stopped
      tty: true
      ports:
        - 8777:80
  ```
* Run the image.

  ```bash
  docker compose up -d
  ```
