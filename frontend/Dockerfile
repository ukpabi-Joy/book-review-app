# Use a supported Node.js LTS base image
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Copy package files first so the dependency layer can be cached
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the frontend source code
COPY . .

# Next.js embeds NEXT_PUBLIC_* variables at build time
ARG NEXT_PUBLIC_API_URL
ENV NEXT_PUBLIC_API_URL=$NEXT_PUBLIC_API_URL

# Create the production build
RUN npm run build

# Expose the Next.js port
EXPOSE 3000

# Start Next.js in production mode
CMD ["npm", "start"]
