# Fairleigh Dickinson University Datamining System

The purpose of this repository is to document and backup for easy reproduction, our server configurations for analysis reproducability.

## Installation

```
mkdir -p fdudatamining
cd fdudatamining
git clone https://github.com/fdudatamining/system.git
git clone https://github.com/fdudatamining/framework.git
cd system
docker-compose up
```

When everything has started visit your hub at `http://localhost/` and navigate to the jupyter-notebook. Work should be saved in `./work`, the database is saved in a docker volume named `data`. PhpMyAdmin sessions are saved in a docker volume named `sessions`.
