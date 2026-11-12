# PROGRAMACION-WEB-T1
Repositorio para actividades en clase y versionamiento en grupo

## Cómo ejecutar el proyecto con Docker
1. Clona el repositorio:
   `git clone <https://github.com/cesar06x/PROGRAMACION-WEB-T1.git>`
2. Construye la imagen de Docker:
   `docker build -t perfil-profesional .`
3. Ejecuta el contenedor:
   `docker run -d -p 8080:80 perfil-profesional`
4. Abre tu navegador en `http://localhost:8080`.