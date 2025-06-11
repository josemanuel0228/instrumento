# Usar versión de nginx estable y ligera
FROM nginx:stable-alpine

# Crear un volumen en /temp
VOLUME /temp

# Eliminar contenido por defecto del servidor Nginx
RUN rm -rf /usr/share/nginx/html/*

# Copiar configuración personalizada de Nginx
COPY nginx.conf /etc/nginx/nginx.conf
COPY mime.types /etc/nginx/mime.types

# Copiar el frontend (Angular o similar) a la carpeta correspondiente
COPY sistema-ventas-front /usr/share/nginx/html

# Exponer el puerto 80 para servir la aplicación web
EXPOSE 80

# Comando para mantener Nginx ejecutándose en primer plano
CMD ["nginx", "-g", "daemon off;"]


