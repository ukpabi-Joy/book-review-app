# Use a supported Node.js LTS base image
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Copy package files first so the dependency layer can be cached
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the backend source code
COPY . .

# Expose the port the backend runs on
EXPOSE 3001

# Start the backend server
CMD ["node", "src/server.js"]
