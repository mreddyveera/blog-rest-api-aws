FROM node:24-alpine3.23 AS build
RUN addgroup -S appgroup && \
    adduser -S appuser -G appgroup
USER appuser
WORKDIR /backend/
COPY --chown=appuser:appuser package*.json ./
RUN --mount=type=cache,target=/root/.npm \
    npm ci
COPY --chown=appuser:appuser . .
CMD ["npm", "run", "dev"]