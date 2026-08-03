# Frontend Dockerfile
FROM node:20-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./
RUN npm install --production=false

# Copy source code
COPY . .

# Build the app
RUN npm run build

# Install serve globally
RUN npm install -g serve

EXPOSE 3000

# Use serve to host the static files
CMD ["serve", "-s", "build", "-l", "3000", "--single"]
## This Dockerfile sets up a Node.js environment for a frontend application.
# It installs dependencies, builds the application, and uses the `serve` package to serve the static files on port 3000.
# here it is just single stage, here it compile to static file 
# this command help it to survive as ststic file CMD ["serve", "-s", "build", "-l", "3000", "--single"]
#--single this means any unknown route will be redirected to index.html, which is useful for single-page applications (SPAs) that handle routing on the client side.
#falls back to index.html this is how react works