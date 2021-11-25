# LibreTrack

An open-source, self-hosted cryptocurrency asset tracker. Track your cryptocurrency transactions, profits/losses, and get a yearly summary for taxes all from the privacy and security of your own server.  

## What are the features?

The following features are currently implemented:

* Basic web application that does almost nothing

The following features are TO-DO:

* Manually add transactions ("Paper Trading")
* Link a public wallet for automatic transaction monitoring
* Link an exchange for automatic transaction monitoring
* End-of-year tax summary


## Setting up

### Clone this Repository & Prepare Server

1. Ensure the server has:  

   * An internet connection (for package and image downloads)
   * Git
   * Docker
   * Docker-Compose

2. Clone this repository to the server of your choice

   ```
   $ git clone https://github.com/kfriede/LibreTrack.git
   $ cd LibreTrack
   ```

### Create and run the images:

```
$ docker-compose up
```

### (First-Run Only) Create database and initial data for development:

```
$ docker-compose exec libretrack ./init_database.sh
```

It will deploy 5 docker images:

- server: Flask app running in [http://localhost:42069](http://localhost:42069).
- worker: Worker ready to get tasks.
- postgres: Postgres SQL isolated from the app.
- adminer: Web client for database management, running in [http://localhost:8080](http://localhost:8080).
- redis: Redis SQL isolated from the app


### Visit the Application in a Web Browser

1. Open your web browser of choice to either:  

   * [http://localhost:42069](http://localhost:42069) (if running locally on your computer)
   * http://<your-server-ip>:42069 (if running on a remote server)

2. Sign in as the administrator user (Default `admin@libretrack.io`:`libretrack`)

## License
[MIT License](LICENSE.md)
