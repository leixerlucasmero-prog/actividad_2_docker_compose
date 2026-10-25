# ---------- Backend: Node.js + Express ----------
FROM node:20-alpine

WORKDIR /app

# Primero solo los package*.json para aprovechar la caché de capas
COPY package*.json ./
RUN npm ci --omit=dev

# Después el código fuente
COPY . .

ENV PORT=5000
EXPOSE 5000

# Ejecutar como usuario sin privilegios (buena práctica de seguridad)
USER node

CMD ["node", "index.js"]
