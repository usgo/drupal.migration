## Summary
Create a docker-compose environment to test the migration of USGO Database and
site update. More or less the docker-compose environment is to help see answer,
"how difficult is transfering the configuration over to a new system?"

## (Required)

### Directories

* `./themes` - contains any additional themes to be installed
* `./modules` - contains any additional modules to be installed

## Create the `themes` and `modules` Directory with:

* `$ mkdir {themes,modules}`

## (Optional)

### Download USGO_WP_API_CONNECT

* `$ git clone git@github.com:usgo/usgo_wp_api_connect.git modules/usgo_wp_api_connect`

### Download Bootstrap Base Theme

```

$ curl -sSL https://ftp.drupal.org/files/projects/bootstrap-8.x-3.23.zip -o /tmp/bootstrap-8.x-3.23.zip && \
    unzip /tmp/bootstrap-8.x-3.23.zip -d themes/ && \
     rm /tmp/bootstrap-8.x-3.23.zip

```

## To Run Use

* `$ docker-compose up`

## Then

* Run through the configuration prompts on http://localhost:8000 to configure a database. If one is running the configuration locally, the configurations are in `.env`. These configurations are only an example, so don't run this on a production system.

### `.env`

```

MYSQL_ROOT_PASSWORD=very_insecure_root_mysql_password
MYSQL_USER=drupal_db_user
MYSQL_DATABASE=drupal_db
MYSQL_PASSWORD=very_insecure_password

```

## References
* https://hub.docker.com/_/drupal/
