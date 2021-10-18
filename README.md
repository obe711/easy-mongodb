# Easy Mongodb

## Install

```bash
git clone https://github.com/obe711/easy-mongodb && cd easy-mongodb
```

## Setup

Edit the hosts file

```bash
sudo nano /etc/hosts
```

Add `127.0.0.1 mongo` to the end of the file:

```bash
127.0.0.1 mongo
```

It should look like this:

```bash
127.0.0.1       localhost
255.255.255.255 broadcasthost
::1             localhost
# Added by Docker Desktop
# To allow the same kube context to work on the host and the container:
127.0.0.1 kubernetes.docker.internal
127.0.0.1 mongo
# End of section
```

Then hit `control + x` then `y` to save

## Running

Make sure Docker Desktop is running, then from the easy-mongodb directory run:

```bash
docker-compose up -d
```

## Update connection strings

You will need to change your connection string to access the mongo db database

- In the app, change `mongodb://localhost:27017` to `mongodb://mongo:27001,mongo:27002,mongo:27003`

- In Compass, create a new connection with `mongodb://mongo:27001,mongo:27002,mongo:27003`

## Troubleshooting

- Stop and then restart the mongodb docker instance

```bash
$ docker-compose down

$ docker-compose up -d


```
