FROM node:24-alpine3.23
RUN addgroup -S appgroup && \
    adduser -S -h /home/appuser -G appgroup
USER appuser
WORKDIR /backend/

COPY --chown=appuser:appgroup package*.json ./
RUN npm ci --omit=dev --cache /home/appuser/.npm
COPY --chown=appuser:appgroup . .
EXPOSE 3000
CMD ["node", "index.js"]
