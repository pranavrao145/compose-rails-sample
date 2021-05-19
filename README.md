# Compose and Rails Sample

A sample development setup with Docker Compose and Rails, using a postgres database.

Recommended Instructions for Use:
* Clone the repository
* Make a new rails project and copy these files to your rails project: 
  * Dockerfile
  * docker-compose.yml 
  * entrypoint.sh
  * config/database.yml (optional if you know what you're doing)
* Add the pg gem to your Gemfile
* Run 
  * docker-compose build
  * docker-compose up
* Go to localhost:3000 to view your Rails app.

NOTE: it is recommended to take a look at the docker-compose.yml and config/database.yml files so you know your database configuration and can make changes as you see fit. If you want to use a DATABASE_URL, you will simply need to replace the default config in config/database.yml with what is in the production config in the same document, and then add a DATABASE_URL to your environment. To add to your environment, you can use docker-compose.yml directly, or using an .env and then registering it in your docker-compose.yml for BOTH db and web services.
