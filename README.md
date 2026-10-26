# U4S8 — Aguayo Gonzalez Edgar Steven

**Grupo:** DSM 4-1 · **Matrícula:** 25311035 · **Materia:** Aplicaciones Web · **Universidad Tecnológica de Hermosillo**

![Python](https://img.shields.io/badge/Python-3.14-blue)
![Django](https://img.shields.io/badge/Django-6.1-green)
![MySQL](https://img.shields.io/badge/MySQL-Aiven-orange)
![Deploy](https://img.shields.io/badge/Deploy-Render-purple)

## Demo y repositorio

- **Repositorio GitHub:** https://github.com/AguayoGonzalezEdgarSteven/u4s8-aguayo-gonzalez-edgar-steven
- **Sitio en producción:** https://u4s8-aguayo-gonzalez-edgar-steven.onrender.com
- **Inicio de sesión:** https://u4s8-aguayo-gonzalez-edgar-steven.onrender.com/login/
- **Servicios:** https://u4s8-aguayo-gonzalez-edgar-steven.onrender.com/servicios/

> **Nota:** Render puede suspender los servicios gratuitos después de un periodo de inactividad. La primera carga puede tardar unos segundos.

## Descripción del proyecto

Aplicación web desarrollada con Django para administrar servicios mediante cuentas de usuario. Cada persona puede registrarse, iniciar sesión y gestionar sus propios servicios.

El sistema incluye operaciones CRUD (crear, consultar, actualizar y eliminar), búsqueda, paginación, autenticación y validación de formularios. La aplicación está preparada para utilizar una base de datos MySQL alojada en la nube y desplegarse en Render.

## Tecnologías utilizadas

| Tecnología | Función |
|---|---|
| Python | Lenguaje de programación principal |
| Django | Framework para desarrollar la aplicación web |
| MySQL en Aiven | Base de datos en la nube |
| PyMySQL | Conexión entre Python y MySQL |
| Tailwind CSS | Diseño y estilos de las páginas |
| Gunicorn | Servidor WSGI para producción |
| WhiteNoise | Administración de archivos estáticos |
| python-decouple | Lectura de variables de entorno |
| Git y GitHub | Control de versiones y alojamiento del código |
| Render | Despliegue y publicación de la aplicación |

## Funcionalidades

- Registro de nuevos usuarios.
- Inicio y cierre de sesión.
- Autenticación mediante el sistema de usuarios de Django.
- Creación de servicios.
- Consulta de los servicios registrados.
- Edición y eliminación de servicios propios.
- Validación de formularios mediante `ModelForm`.
- Validación personalizada del precio mediante `clean_precio`.
- Búsqueda de servicios por título.
- Paginación del listado de servicios.
- Restricción de acceso a los servicios de otros usuarios.
- Mensajes informativos para las acciones realizadas.
- Diseño adaptable a diferentes tamaños de pantalla.

## Estructura del proyecto

```text
miproyecto-django_ages/
├── core/
│   ├── models.py
│   ├── forms.py
│   ├── views.py
│   ├── urls.py
│   └── templates/
│       └── core/
│           ├── base.html
│           ├── inicio.html
│           ├── servicios.html
│           ├── servicio_form.html
│           ├── servicio_confirm_delete.html
│           ├── registro.html
│           └── login.html
├── miproyecto_ages/
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
├── manage.py
├── requirements.txt
├── .gitignore
└── README.md
```

*Nota: la estructura anterior representa la organización esperada del proyecto; los archivos y directorios exactos pueden variar según la versión de tu repositorio.*

## Rutas principales

| Ruta | Descripción | Acceso |
|---|---|---|
| `/` | Página
