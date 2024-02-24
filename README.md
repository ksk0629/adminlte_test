# LARAVEL PROJECT
This repository is for creating a new laravel project.

# Setup
## Adjust settings
1. Set the user and the password for the database in `./docker-compose.yml`.
2. Set the project name in `./docker/app/000-default.conf`.

## Docker container
1. Create the comtainers: `docker-compose build`.
2. Kick the containers: `docker-compose up -d`.

## Laravel
### Project creation
1. Go into the container: `docker exec -it laravel_app bash`.
2. Install Laravel: `composer require laravel/installer`.
3. Add the composer path to the environment variables $PATH: `export PATH=/var/www/html/vendor/bin:$PATH`.
4. Create a laravel project: `laravel new [project_name]`.
5. Change the current directory to the new project: `cd [project_name]`.

### Environment settings
1. Set the encryption key: `php artisan key:generate`.
2. Change the rights of the log directory: `chmod 777 storage/logs/`.
3. Change the rights of the storage directory: `chmod -R guo+w storage`.
4. Install the lates Node via nvm: `nvm install --lts`.
5. Update npm: `npm update`.
6. Update the database settings in `.env`.
    - `DB_HOST` should be the name of the database container.
    - `DB_DATANAME` should be the database set in `docker-compose.yml`.
    - `DB_USERNAME` should be the user name set in `docker-compose.yml`.
    - `DB_PASSWORD` should be the password set in `docker-compose.yml`.

## Have a look!
http://localhost:8000

# Trouble shooting
- Q. How to connect to the database?
    - A. Go into the db container: `docker exec -it laravel_db bash`.
