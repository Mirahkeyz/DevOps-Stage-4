# Use Node.js 14 Alpine as the base image
FROM node:14-alpine

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json (if available)
COPY package*.json ./

RUN rm -rf node_modules package-lock.json #add package-lock.json removal.
RUN npm cache clean --force #clear the cache.

# Install dependencies
RUN npm install

# Copy the entire project
COPY . .

# Build the Vue.js app
RUN npm run build

# Expose the port the app will run on
EXPOSE 8080

# Run the application in development mode
CMD ["npm", "run", "start"]
