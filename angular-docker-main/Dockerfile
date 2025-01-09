######## WITHOUT multi stage ########
FROM node:alpine

WORKDIR /usr/src/app

COPY . /usr/src/app

RUN npm install -g @angular/cli

RUN npm install

CMD ["ng", "serve", "--host", "0.0.0.0"]

########### MULTI stage #############

# # Stage 1: Build
# FROM node:alpine AS build

# WORKDIR /usr/src/app

# # Copy package.json and package-lock.json to leverage Docker cache
# COPY package*.json ./

# # Install dependencies
# RUN npm install

# # Copy the rest of the application code
# COPY . .

# # Build the Angular app
# RUN npm install -g @angular/cli && ng build --configuration production

# # Stage 2: Runtime
# FROM nginx:alpine

# # Copy built files from the build stage to the NGINX directory
# COPY --from=build /usr/src/app/dist/* /usr/share/nginx/html

# # Expose the default NGINX port
# EXPOSE 80

# # Start NGINX
# CMD ["nginx", "-g", "daemon off;"]
