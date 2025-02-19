FROM node:23.0-alpine

WORKDIR /app/frontend

COPY package*.json .

RUN npm install

COPY . .

# Next.js listens on port 3000 by default
EXPOSE 3000

# Uncomment the line below to run in development mode with live reloading
CMD ["npm", "run", "dev"]