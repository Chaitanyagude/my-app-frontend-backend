# Stage 1: Build the React application
FROM node:latest as build

# Set the working directory in the build stage
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Bundle app source
COPY . .

# Build the React application
RUN npm run build

# Stage 2: Serve the app with Nginx
FROM nginx:alpine

# Copy the build artifacts from the build stage to Nginx's serve directory
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80 to the outside once the container has launched
EXPOSE 80

# Start Nginx and keep it running in the foreground
CMD ["nginx", "-g", "daemon off;"]

