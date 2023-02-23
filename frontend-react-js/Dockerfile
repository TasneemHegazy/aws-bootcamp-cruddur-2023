# Build stage
FROM node:16.18 AS build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Runtime stage
FROM node:16.18-slim
ENV NODE_ENV=production
WORKDIR /app
COPY --from=build /app/build /app
EXPOSE 3000
CMD ["./start.sh"]