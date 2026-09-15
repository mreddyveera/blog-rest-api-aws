FROM node:24-alpine3.23

RUN addgroup -S appgroup && \
    adduser -S -G appgroup
USER appuser
WORKDIR /backend/

COPY --chown=appuser:appgroup package*.json ./

RUN npm ci

COPY --chown=appuser:appgroup . .

EXPOSE 3000

CMD ["node", "index.js"]