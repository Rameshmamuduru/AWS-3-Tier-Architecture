# Use official Node image (Node 16, matches your EC2 setup)
FROM node:16-alpine

# Set working directory
WORKDIR /app

# Install PM2 globally
RUN npm install -g pm2

# Copy package.json and package-lock.json first (for caching)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of your application code
COPY . .

# Expose the port your app listens on
EXPOSE 400    # or whatever port your app uses internally

# Start the app with PM2 runtime (replaces pm2 startup/save)
CMD ["pm2-runtime", "index.js"]