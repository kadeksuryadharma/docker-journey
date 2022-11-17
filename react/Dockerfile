# Build phase
FROM node:18-alpine as builder

WORKDIR '/app'

COPY ./package.json ./
RUN npm install

COPY ./ ./
RUN npm run build


# Production run using Nginx
FROM nginx

# Copy from builder phase
COPY --from=builder /app/build /usr/share/nginx/html
