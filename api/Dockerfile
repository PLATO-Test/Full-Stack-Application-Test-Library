# Use Node.js 18 Alpine (lightweight Linux distribution)
FROM node:18-alpine

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json for dependency installation
# Copying these first allows Docker to cache this layer if dependencies haven't changed
COPY package*.json ./

# Install build tools needed to compile native modules like sqlite3
# These are required because sqlite3 needs to be compiled for Alpine Linux
RUN apk add --no-cache python3 make g++

# Install only production dependencies (excludes devDependencies like nodemon)
# npm ci is faster and more reliable than npm install for automated environments
# This will rebuild sqlite3 for the Alpine Linux environment
RUN npm ci --only=production

# Copy all application source code into the container
COPY . .

# Expose port 5000 so the API can receive traffic
# This is documentation - you still need to map ports when running the container
EXPOSE 5000

# Start the application using node directly (not nodemon which is for development)
CMD ["node", "app.js"]