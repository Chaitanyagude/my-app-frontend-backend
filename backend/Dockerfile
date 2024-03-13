# Use the official Node.js 16 as a parent image
FROM node:latest

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json (or yarn.lock)
COPY package*.json ./

# Install any dependencies
RUN npm install


# Bundle the app source inside the Docker image
COPY . .

# Your application's default port, e.g., 3000 for Express
EXPOSE 3000

# Command to run the app
CMD ["npm", "start"]


