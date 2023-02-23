# Build stage
FROM node:16.18.0 AS build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build && \
    rm -rf node_modules && \
    npm install --production && \
    npm cache clean --force

# Runtime stage
FROM node:16.18.0-slim
ENV NODE_ENV=production
WORKDIR /app
COPY --from=build /app /app
RUN addgroup --system --gid 1001 appgroup && \
    adduser --system --uid 1001 --ingroup appgroup appuser && \
    chown -R appuser:appgroup /app && \
    chmod -R g=u /app
USER appuser
EXPOSE 3000
CMD ["./start.sh"]