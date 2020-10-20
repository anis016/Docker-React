## Run Start (Development)

`npm run start` Starts up a development server. This is used for Development only.

```
# build: Dockerfile.dev
$ docker build -t anis016/frontend -f Dockerfile.dev .
// delete the node_modules from the frontend folder to reduce the space
// rebuild the image again using the same command above and then create the container using the below command 
$ docker run -it -p 3000:3000 -v /app/node_modules -v $(pwd):/app anis016/frontend
```

## Run Test (Development)

`npm run test` Run tests associated with the project. This is used for the Development.

```
# build: docker-compose.yml
$ docker-compose up
// If need to check the details of the tests and to use interactivity then use "-it" 
$ docker container run -it frontend_tests npm run test
// To check the coverage use the --coverage
$ docker container run frontend_tests npm run test -- --coverage
```


## Run Build (Production)

`npm run build` Builds the production version of the application.

```
# build: Dockerfile
$ docker build -t anis016/frontend-prod .
$ docker run -p 8080:80 anis016/frontend-prod:latest
```