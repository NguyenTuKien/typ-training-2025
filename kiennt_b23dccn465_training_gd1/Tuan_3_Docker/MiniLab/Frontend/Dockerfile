# syntax=docker/dockerfile:1
FROM node:18-alpine AS frontend-build
WORKDIR /app
COPY package*.json ./
# Install all deps including dev (vite)
RUN npm ci
# Safety: ensure vite exists (remove after confirming)
RUN grep -i vite package.json && npm ls vite || npm install -D vite
COPY . .
RUN npx vite build

FROM nginx:alpine AS production
ENV NODE_ENV=production
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=frontend-build /app/dist /usr/share/nginx/html
EXPOSE 5173
CMD ["nginx","-g","daemon off;"]
