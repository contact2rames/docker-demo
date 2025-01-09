# Multi Containers App

This is a repo for new users getting started with Docker.

You can try it out using the following command.

```docker compose up -d```

And open http://localhost:3000 in your browser.

This is a simple todo application built using ExpressJS and Node.js, which saves all todos in a MongoDB database.

This compose file defines two services, app and mongodb.
The app service maps port 3000 of the container to port 3000 of the host, sets the working directory inside the container to /app, and mounts the current directory on the host to /app inside the container. 

># develop-watch

``` docker-compose watch   //docker compose alpha watch  ```

This allows you to monitor changes to your source code and based on your requirement you can do following actions.
sync – syncs the source code from local system to container(The "sync" action specifies a path to watch for changes in the host file system, and a corresponding target path inside the container to synchronize changes to)
rebuild – automatically restart containers(The "rebuild" action specifies a path to watch for changes in the host file system, and triggers a rebuild of the container when changes are detected.)

```Validation:```
Open app/views/todos.ejs in a text or code editor, then change the text on line 18.
Save the changes in app/views/todos.ejs.
View your application at http://localhost:3000 to see the changes in real-time.

># Dockerfile

--mount=type=bind: Mounts the package.json and package-lock.json from the host to the container.This avoids copying the files into the container during this layer, optimizing the build.

Cache Mount: --mount=type=cache,target=/root/.npm: Uses a cache for npm modules to speed up subsequent builds by storing dependencies.

npm ci: Ensures clean installation based on package-lock.json.

The --include=dev flag installs development dependencies as they are needed for the next steps.

RUN npm install -g nodemon: Installs nodemon globally in the container to enable hot-reloading during development.

CMD npm run dev(or CMD npm start, for prod): npm run dev typically starts the app in development mode, allowing hot-reloading with tools like nodemon.
