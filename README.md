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

## Extra Notes 

* It is recommended to take a look at the docker-compose.yml and config/database.yml files so you know your database configuration and can make changes as you see fit. If you want to use a DATABASE_URL, you need to:
  * Replace the default config in config/database.yml with what is in the production config in the same document. 
  * Add a DATABASE_URL to your environment. To add to your environment, you can do one of the following:
    * Use docker-compose.yml ENVIRONMENT directly
    * Create .env and then registering it in your docker-compose.yml for BOTH db and web services using env_file.

* If you are using this template to dockerize an existing rails project, there are some issues with yarn and an empty manifest.json. So, for this setup to work, you need to manually run *docker-compose run web bash*, and then run:
  * yarn
  * rails webpacker:compile

  * Don't forget to verify (again) your database configuration (see above) to make sure your setup is compatible with what is given in this template; fix whatever is necessary to make sure postgres is set up, the credentials are correct, and any environment variables are set.
  
   
