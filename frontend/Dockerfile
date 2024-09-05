# Fase 1: Construcción de la aplicación
FROM node:18-alpine AS builder

# Establece el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copia los archivos de package.json y package-lock.json
COPY package*.json ./

# Instala TODAS las dependencias (incluidas las de desarrollo)
RUN npm install

# Copia el resto del código de la aplicación
COPY . .

# Construye la aplicación de Next.js para producción
RUN npm run build

# Fase 2: Imagen final con la aplicación construida
FROM node:18-alpine

# Establece el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copia solo las dependencias de producción desde la fase anterior
COPY --from=builder /app/node_modules ./node_modules

# Copia los archivos necesarios de la aplicación
COPY --from=builder /app/.next ./.next
COPY --from=builder /app/package*.json ./

# Expone el puerto en el que correrá la aplicación
EXPOSE 3000

# Comando para ejecutar la aplicación
CMD ["npm", "start"]
