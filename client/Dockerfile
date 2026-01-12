# Use Node.js 18 Alpine (lightweight Linux distribution)
FROM node:18-alpine

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json for dependency installation
# Copying these first allows Docker to cache this layer if dependencies haven't changed
COPY package*.json ./

# Install only production dependencies (excludes devDependencies like nodemon)
# npm ci is faster and more reliable than npm install for automated environments
# This will rebuild sqlite3 for the Alpine Linux environment
RUN npm ci

# Copy all application source code into the container
COPY . .

EXPOSE 3000

# Start the application using node directly (not nodemon which is for development)
CMD ["npm", "start"]