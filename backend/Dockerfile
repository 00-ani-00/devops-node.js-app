# Stage 1: Build the Node.js application
FROM node:14 AS backend
WORKDIR /app
COPY backend/package*.json ./
RUN npm install
COPY backend .
RUN npm run build

# Stage 2: Create a lightweight image for runtime
FROM node:14-alpine
WORKDIR /app
COPY --from=backend /app/dist ./dist
COPY --from=backend /app/node_modules ./node_modules
EXPOSE 3000
CMD ["node", "dist/index.js"]
