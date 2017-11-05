# Fairleigh Dickinson University Datamining System

The purpose of this repository is to document and backup for easy reproduction, our server configurations for analysis reproducability.

## Installation

```
# Create working directory
mkdir -p fdudatamining
cd fdudatamining

# Clone relevant repositories
git clone https://github.com/fdudatamining/system.git
git clone https://github.com/fdudatamining/framework.git

# Create random secure password for database root
cd system
MYSQL_ROOT_PASSWORD=your_secret_password docker-compose up
# Wait for the system to be completely built and come up

# Populate the database with data
git clone https://github.com/fdudatamining/data.git
cd data
docker build -t fdudatamining:data .
docker run -e MYSQL_ROOT_PASSWORD=your_secret_password -it fdudatamining:data

# Point your favorite web browser to http://localhost/
```

Work should be saved in `./work`, the database is saved in a docker volume named `data`. PhpMyAdmin sessions are saved in a docker volume named `sessions`.

## Cleanup

Note that volumes are persistent accross instances--if something failed and you want a clean slate, execute:

```
docker-compose rm -v
```
