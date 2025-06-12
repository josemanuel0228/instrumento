# Usar la imagen base de Node.js
FROM node:18.17.1-alpine

# Crear directorio de trabajo
WORKDIR /usr/src/app

# Copiar archivos de dependencias
COPY package*.json .

# Instalar dependencias
RUN npm install

# Copiar todo el proyecto al contenedor
COPY . .

# Exponer el puerto 3000
EXPOSE 3000

# Comando para ejecutar la app
CMD ["node", "index.js"]
