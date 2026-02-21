# proyecto-6
Lizander Cross 2021-1754

# 🚀 Servidor Web Nginx con Docker Compose

## 📖 Descripción

Este proyecto implementa un servidor web **Nginx** ejecutándose en un contenedor Docker, administrado mediante **Docker Compose**.  

El servidor sirve un archivo `index.html` ubicado en un volumen montado desde el directorio local `src`, permitiendo modificar el contenido sin reconstruir la imagen.

---

## 🎯 Objetivos de la Práctica

- Comprender el uso básico de Docker Compose.
- Implementar un servidor web Nginx en contenedor.
- Configurar volúmenes para servir contenido estático.
- Exponer puertos para acceso desde el navegador.
- Versionar el proyecto con Git y publicarlo en GitHub.

---

## 🧱 Estructura del Proyecto

nginx-practica/
│
├── docker-compose.yml # Configuración del servicio Nginx
├── README.md # Documentación del proyecto
└── src/
└── index.html # Página web servida por Nginx

---

## 🐳 Configuración de Docker Compose

Archivo: `docker-compose.yml`

```yaml
services:
  web:
    image: nginx:latest
    container_name: nginx_local
    ports:
      - "8080:80"
    volumes:
      - ./src:/usr/share/nginx/html
    restart: always
