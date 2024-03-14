FROM node:lts-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .  
FROM node:lts-alpine
WORKDIR /app
COPY --from=builder /app/build /app
# Expose port (adjust if needed)
EXPOSE 80
CMD [ "npm", "start" ]