#docker file Front

# Etapa 1: Construir la aplicación React
FROM node:14.15.3-alpine3.12 as build

# Establecer el directorio de trabajo
WORKDIR /usr/src/app

# Copiar archivos necesarios e instalar dependencias
COPY package*.json ./
RUN npm install

# Copiar el resto del código fuente y construir la aplicación
COPY . .
RUN npm run build

# Etapa 2: Servir la aplicación con Nginx
FROM nginx:1.21.0-alpine

# Copiar los archivos de compilación al directorio predeterminado de Nginx
COPY --from=build /usr/src/app/build /usr/share/nginx/html

# Exponer el puerto
EXPOSE 80

# Iniciar Nginx
CMD ["nginx", "-g", "daemon off;"]
