#Dockerfile Back

# Utilizar Node.js en un entorno optimizado para producción
FROM node:14.15.3-alpine3.12

# Establecer variable de entorno
ENV NODE_ENV=production

# Crear directorio de la aplicación
WORKDIR /usr/src/app

# Copiar solo los archivos necesarios para instalar dependencias
COPY package*.json ./

# Instalar solo las dependencias de producción
RUN npm install --production

# Copiar el resto del código fuente
COPY . .

# Exponer el puerto en el que escucha el servidor
EXPOSE 8080

# Comando para iniciar el servidor
CMD ["node", "server.js"]
