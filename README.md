### Setting up new project:
1. Clone the repository
2. To build and run docker: `docker compose up -d --build` 
3. To create symfony skeleton:
   1. Remove `.gitignore` file from app directory as dir should be empty before creation of the project.
   2. Run: `docker exec -it php81-container bash` to run docker terminal
   3. Run `composer create-project symfony/skeleton .` to generate new symfony project
   4. Run: `symfony check:req` to test whether symfony is ready to run (it should be)
   5. Run: `composer require doctrine` to add doctrine dependency
   6. Go to app/.env file to correct DATABASE_URL config (set user, password, server version, port to match config from docker-compose file, db name should be define there too)
   7. Run: `composer require encore` to install
   8. Run: `yarn add react react-dom prop-types` to install react and its dependencies
   9. Enable react preset in webpack config: `Encore.enableReactPreset()` and restart encore (run `yarn run dev`).
   10. Run `exit` to go out from docker context
4. Run `git init` from app directory context to initialize git repository and add all project files

### Running project
1. `docker compose up -d`
2. `docker compose run --rm node-service yarn install`
3. `docker compose run --rm node-service yarn dev`
