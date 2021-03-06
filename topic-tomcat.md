# Docker Compose

- In the `docker-compose.yml` file, 
  properties under `services` are called context.
    
- For example:
  ```
  version: "3.8"
  services:
    mongodb:
      image: mongodb
      build:
      context: ./mongodb
      ports:
      - "27017:27017"
    api:
      image: rss_trendy_api
      build:
        context: ./api
        dockerfile: Dockerfile.dev
      volumes:
      - /app/node_modules
      - ./api:/app
      environment:
      - mongoDBServer=mongoDB
      ports:
      - "5000:5000"
      links:
      - mongodb
    client:
      image: rss_trendy_client
      build:
      context: ./client
      dockerfile: Dockerfile.dev
      volumes:
      - /app/node_modules
      - ./client:/app
      ports:
      - "3000:3000"	
  ```
  
  `mongodb`, `api`, and `client` are three contexts in this docker compose.
