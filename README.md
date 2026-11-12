# Portafolio Profesional - Programación Web (T1)

Sitio web estático y responsivo de portafolio profesional desarrollado de forma colaborativa aplicando flujo de trabajo Git/GitHub (Issues, Feature Branches, Pull Requests y Code Reviews) y contenerizado con **Docker** sobre **Nginx**.

---

## 🏗️ Arquitectura y Estructura del Proyecto

El proyecto implementa una arquitectura ligera basada en un servidor web **Nginx (`nginx:alpine`)** que sirve los activos estáticos (HTML5, CSS3 y recursos multimedia) desde el directorio `src/`:

```text
PROGRAMACION-WEB-T1/
├── src/
│   ├── css/
│   │   └── perfil.css        # Hoja de estilos principal (Variables CSS, Grid, Flexbox y Media Queries)
│   ├── recursos/
│   │   └── perfil.jpeg       # Fotografía y recursos gráficos del perfil
│   ├── Dockerfile            # Configuración de la imagen Docker basada en nginx:alpine
│   └── index.html            # Estructura semántica principal del portafolio
└── README.md                 # Documentación técnica y guía de despliegue
```

### Tecnologías Utilizadas
* **Frontend:** HTML5 Semántico, CSS3 (Custom Properties, CSS Grid, Flexbox, Diseño Responsivo).
* **Contenerización y Servidor Web:** Docker, Docker Hub, Nginx (`nginx:alpine`).
* **Control de Versiones:** Git & GitHub (Flujo colaborativo con ramas `feat/*` y `docs/*`, Issues y Pull Requests).

---

## 🚀 Instrucciones de Despliegue con Docker

### Opción 1: Ejecutar directamente desde Docker Hub (Recomendado)

La imagen oficial del proyecto se encuentra publicada en Docker Hub bajo el repositorio `joseph323123/programacion-web-t1`.

1. **Descargar la imagen desde Docker Hub:**
   ```bash
   docker pull joseph323123/programacion-web-t1:latest
   ```

2. **Iniciar el contenedor mapeando el puerto `8080`:**
   ```bash
   docker run -d -p 8080:80 --name portafolio-web joseph323123/programacion-web-t1:latest
   ```

3. **Visualizar en el navegador:**
   Ingresa a 👉 [http://localhost:8080](http://localhost:8080)

---

### Opción 2: Construir la imagen localmente desde el repositorio

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/cesar06x/PROGRAMACION-WEB-T1.git](https://github.com/cesar06x/PROGRAMACION-WEB-T1.git)
   cd PROGRAMACION-WEB-T1
   ```

2. **Construir la imagen indicando el contexto `src/`:**
   ```bash
   docker build -t joseph323123/programacion-web-t1:latest -f src/Dockerfile ./src
   ```

3. **Ejecutar el contenedor:**
   ```bash
   docker run -d -p 8080:80 --name portafolio-local joseph323123/programacion-web-t1:latest
   ```

4. **Detener y eliminar el contenedor (opcional):**
   ```bash
   docker rm -f portafolio-local
   ```

---

## 🔄 Flujo de Trabajo Colaborativo (Git / GitHub)

El proyecto se construyó de manera modular dividiendo responsabilidades en ramas e Issues revisados mediante Pull Requests:
1. **Integrante 1 (`feat/estructura-html`):** Maquetación semántica en `src/index.html` (Encabezado, Descripción, Habilidades, Línea de Tiempo, Portafolio y Contacto).
2. **Integrante 2 (`feat/diseno-responsivo`):** Diseño UI en `src/css/perfil.css` con paleta oscura y acentos dorados, animaciones *hover*, Grid/Flexbox y adaptabilidad móvil (`@media`).
3. **Integrante 3 (`feat/docker-deploy` / `docs/readme-docker`):** Configuración de `src/Dockerfile`, publicación de la imagen en Docker Hub y documentación técnica del repositorio.