# Stage 1: Build the React App
FROM node:16 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Serve the React App
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
ENV HOST=0.0.0.0
EXPOSE 3000
CMD ["nginx", "-g", "daemon off;"]
