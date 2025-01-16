# Stage 1: Build
FROM node:14-alpine AS build
WORKDIR /home/ubuntu/youtube-clone

# Copy package.json and package-lock.json and install dependencies
COPY package*.json ./
RUN npm ci --only=production && npm cache clean --force

# Copy the rest of the application source code
COPY . .

# Stage 2: Run
FROM node:14-alpine AS runtime
WORKDIR /home/ubuntu/youtube-clone

# Copy the built application from the previous stage
COPY --from=build /home/ubuntu/youtube-clone .

# Expose the application's port
EXPOSE 3000

# Set the command to run the application
CMD ["npm", "start"]