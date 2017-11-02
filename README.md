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
git clone https://github.com/fdudatamining/data.git

# Create random secure password for database root
cd system
MYSQL_ROOT_PASSWORD=your_secret_password docker-compose up
# Wait for the system to be completely built and come up

# Populate the database with data
cd data
MYSQL_ROOT_PASSWORD=your_secret_password python ./setup.py install

# Point your favorite web browser to http://localhost/
```

Work should be saved in `./work`, the database is saved in a docker volume named `data`. PhpMyAdmin sessions are saved in a docker volume named `sessions`.
