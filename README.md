# U4S8 — Aguayo Gonzalez Edgar Steven

**Grupo:** DSM 4-1 · **Matrícula:** 25311035 · **Materia:** Aplicaciones Web · **Universidad Tecnológica de Hermosillo**

![Python](https://img.shields.io/badge/Python-Django-blue)
![Django](https://img.shields.io/badge/Framework-Django-green)
![MySQL](https://img.shields.io/badge/Database-MySQL-orange)
![Render](https://img.shields.io/badge/Deploy-Render-purple)
![GitHub](https://img.shields.io/badge/Code-GitHub-black)

## Demo en vivo y repositorio

- **Repositorio GitHub:** https://github.com/AguayoGonzalezEdgarSteven/u4s8-aguayo-gonzalez-edgar-steven
- **Sitio en Render:** https://u4s8-aguayo-gonzalez-edgar-steven.onrender.com
- **Inicio de sesión:** https://u4s8-aguayo-gonzalez-edgar-steven.onrender.com/login/
- **Servicios:** https://u4s8-aguayo-gonzalez-edgar-steven.onrender.com/servicios/

> **Nota:** Los servicios gratuitos de Render pueden entrar en suspensión después de un periodo de inactividad. La primera visita puede tardar unos segundos en cargar.

## Descripción del proyecto

U4S8 es la práctica final de la materia Aplicaciones Web. Consiste en una aplicación desarrollada con Django y Python para administrar servicios mediante cuentas de usuario.

El proyecto integra los conocimientos adquiridos durante el curso: estructura de una aplicación web, diseño con HTML y Tailwind CSS, conexión con una base de datos MySQL, operaciones CRUD, formularios, autenticación, sesiones, búsqueda, paginación y despliegue en la nube.

Cada usuario puede registrarse, iniciar sesión y administrar sus propios servicios. La aplicación está preparada para trabajar con MySQL en Aiven y publicarse en Render.

## Tecnologías utilizadas

| Tecnología | Uso |
|---|---|
| Python | Lenguaje principal del backend |
| Django | Framework para desarrollar la aplicación |
| MySQL en Aiven | Base de datos en la nube |
| PyMySQL | Conexión de Python con MySQL |
| HTML5 | Estructura de las páginas |
| Tailwind CSS | Diseño y estilos responsivos |
| Gunicorn | Servidor WSGI para producción |
| WhiteNoise | Administración de archivos estáticos |
| python-decouple | Lectura de variables de entorno |
| Git y GitHub | Control de versiones y almacenamiento del código |
| Render | Despliegue y publicación de la aplicación |

## Funcionalidades principales

- Registro de usuarios.
- Inicio y cierre de sesión.
- Autenticación mediante `django.contrib.auth`.
- Creación, consulta, edición y eliminación de servicios.
- Validación de formularios con `ModelForm`.
- Validación personalizada del precio mediante `clean_precio`, si está implementada en la versión desplegada.
- Búsqueda de servicios por título.
- Paginación de resultados.
- Acceso restringido a los servicios de cada usuario.
- Mensajes informativos para las acciones realizadas.
- Diseño adaptable a computadoras y dispositivos móviles.
- Configuración para despliegue en Render.

## Estructura del proyecto

```text
u4s8-aguayo-gonzalez-edgar-steven/
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

*La estructura es orientativa. Los archivos y las plantillas deben coincidir con los que realmente existen en el repositorio.*

## Rutas principales

| Ruta | Descripción | Acceso |
|---|---|---|
| `/` | Página de inicio | Público |
| `/registro/` | Registro de usuarios | Público |
| `/login/` | Inicio de sesión | Público |
| `/logout/` | Cierre de sesión | Usuario autenticado |
| `/servicios/` | Listado de servicios | Usuario autenticado |
| `/servicios/nuevo/` | Crear un servicio | Usuario autenticado |
| `/servicios/<id>/editar/` | Editar un servicio | Según permisos |
| `/servicios/<id>/eliminar/` | Eliminar un servicio | Según permisos |
| `/admin/` | Administración de Django | Superusuario |

## Seguridad y configuración

Para ejecutar el proyecto en producción, las credenciales y configuraciones sensibles deben mantenerse fuera del código público.

| Variable | Función |
|---|---|
| `SECRET_KEY` | Firma de sesiones y otros componentes de seguridad de Django |
| `DEBUG` | Activa o desactiva el modo de depuración |
| `ALLOWED_HOSTS` | Define los dominios permitidos |
| `CSRF_TRUSTED_ORIGINS` | Configura los orígenes de confianza para formularios |
| `DB_NAME` | Nombre de la base de datos |
| `DB_USER` | Usuario de la base de datos |
| `DB_PASSWORD` | Contraseña de la base de datos |
| `DB_HOST` | Servidor de la base de datos |
| `DB_PORT` | Puerto de conexión |

El archivo `.env` debe excluirse de Git mediante `.gitignore`. En producción, `DEBUG` debe estar desactivado y las credenciales deben configurarse en el panel de Render.

## Cómo ejecutar el proyecto en local

### 1. Clonar el repositorio

```bash
git clone https://github.com/AguayoGonzalezEdgarSteven/u4s8-aguayo-gonzalez-edgar-steven.git
cd u4s8-aguayo-gonzalez-edgar-steven
```

### 2. Crear el entorno virtual

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Instalar las dependencias

```bash
pip install -r requirements.txt
```

### 4. Configurar las variables de entorno

Crea el archivo `.env` en la raíz del proyecto y agrega las variables requeridas por `settings.py`.

Ejemplo orientativo:

```dotenv
SECRET_KEY=tu_clave_secreta
DEBUG=True
ALLOWED_HOSTS=127.0.0.1,localhost
DB_NAME=nombre_de_base
DB_USER=usuario
DB_PASSWORD=contrasena
DB_HOST=host_de_mysql
DB_PORT=3306
```

Los nombres deben coincidir con los que utiliza tu configuración de Django. No publiques tus credenciales reales.

### 5. Aplicar las migraciones

```bash
python manage.py migrate
```

### 6. Ejecutar el servidor

```bash
python manage.py runserver
```

Abre el sitio local en:

http://127.0.0.1:8000/

## Despliegue en Render

**Build Command**

```bash
pip install -r requirements.txt && python manage.py collectstatic --noinput && python manage.py migrate
```

**Start Command**

```bash
gunicorn miproyecto_ages.wsgi:application
```

El módulo `miproyecto_ages` corresponde al nombre de configuración que apareció en el registro local de Django. Si la ubicación de `wsgi.py` cambia, el comando deberá ajustarse.

Configura en Render las variables de entorno requeridas por la aplicación y verifica que la conexión con MySQL funcione correctamente.

---

# Historial del curso — unidades y prácticas

## Unidad 1 · Fundamentos de desarrollo web

**Objetivo:** aprender a estructurar páginas web y presentar información mediante HTML y estilos con Tailwind CSS.

| Práctica | Tema | Enlaces |
|---|---|---|
| U1S1 | Creación y publicación de un portafolio estático | [GitHub](https://github.com/AguayoGonzalezEdgarSteven/portafolio_ESAG) |
| U1S2 | Diseño de una página personal con Tailwind CSS | [GitHub](https://github.com/AguayoGonzalezEdgarSteven/ine_personal_ESAG) · [Render](https://ine-personal-esag.onrender.com) |

**Resumen de la unidad:** se desarrollaron páginas web estáticas, se trabajó con HTML5 y Tailwind CSS y se publicaron los primeros proyectos en internet mediante Render.

## Unidad 2 · Django y bases de datos MySQL

**Objetivo:** introducir el desarrollo del backend con Django y conectar la aplicación con una base de datos en la nube.

| Práctica | Tema | Enlaces |
|---|---|---|
| Unidad 2 · Proyecto Django | Aplicación Django conectada con MySQL en Aiven | [GitHub](https://github.com/AguayoGonzalezEdgarSteven/miproyecto_django_aiven_ages) · [Render](https://crud-admin-servicios-aivin-sjqy.onrender.com) |

**Resumen de la unidad:** se trabajó con proyectos Django, configuración de bases de datos MySQL, modelos, migraciones y administración de registros. También se practicó la publicación de aplicaciones web en Render.

*El `index.html` proporcionado contiene dos bloques de enlaces para esta unidad, pero apuntan al mismo repositorio y al mismo sitio. Por eso se consolidaron en una sola entrada para evitar duplicados.*

## Unidad 3 · Operaciones CRUD y autenticación

**Objetivo:** desarrollar aplicaciones dinámicas que permitan gestionar información y controlar el acceso de los usuarios.

| Práctica | Tema | Enlaces |
|---|---|---|
| U3S5 | Desarrollo de una aplicación web con operaciones CRUD | [GitHub](https://github.com/AguayoGonzalezEdgarSteven/u3s5-aguayo-gonzalez-edgar-steven) · [Render](https://u3s5-aguayo-gonzalez-edgar-steven.onrender.com) |
| U3S6 | Continuación del proyecto Django y gestión de usuarios | [GitHub](https://github.com/AguayoGonzalezEdgarSteven/u3s6-aguayo-gonzalez-edgar-steven) · [Render](https://u3s6-aguayo-gonzalez-edgar-steven.onrender.com) |

**Resumen de la unidad:** se avanzó en la creación de aplicaciones dinámicas, el manejo de registros, los formularios y la interacción con la base de datos. También se trabajó con la autenticación y el control de sesiones para proteger las funcionalidades de la aplicación.

## Unidad 4 · Proyecto integrador y despliegue final

**Objetivo:** integrar los conocimientos del curso mediante una aplicación Django que permita administrar servicios y publicarse en un entorno de producción.

| Práctica | Tema | Enlaces |
|---|---|---|
| U4S7 | Búsqueda, paginación y mejoras de experiencia de usuario | [GitHub](https://github.com/AguayoGonzalezEdgarSteven/u4s7-aguayo-gonzalez-edgar-steven) · [Render](https://u4s7-aguayo-gonzalez-edgar-steven.onrender.com/login/) |
| U4S8 | Integración final, documentación y despliegue | [GitHub](https://github.com/AguayoGonzalezEdgarSteven/u4s8-aguayo-gonzalez-edgar-steven) · [Render](https://u4s8-aguayo-gonzalez-edgar-steven.onrender.com/login/) |

**Resumen de la unidad:** se integraron las funcionalidades de la aplicación, incluyendo autenticación, gestión de servicios, búsqueda y paginación. También se preparó el proyecto para producción mediante variables de entorno, administración de archivos estáticos, migraciones y despliegue en Render.

## Qué se trabajó durante el curso

- **Semana 1:** creación de un sitio web estático y publicación en Render.
- **Semana 2:** diseño de páginas web mediante Tailwind CSS.
- **Semana 3:** desarrollo con Django y conexión a MySQL en Aiven.
- **Semana 4:** modelos, migraciones, rutas y configuración del servidor.
- **Semana 5:** operaciones CRUD y validación de formularios.
- **Semana 6:** registro, autenticación, sesiones y protección de rutas.
- **Semana 7:** búsqueda, paginación y mejoras de interfaz.
- **Semana 8:** integración final, configuración de producción, documentación y despliegue.

*Los resúmenes describen los objetivos generales de las prácticas con base en el historial disponible; no sustituyen la comprobación del contenido de cada repositorio.*

## Autor

**Aguayo Gonzalez Edgar Steven**

- **Carrera:** TSU en Desarrollo de Software Multiplataforma
- **Grupo:** DSM 4-1
- **Matrícula:** 25311035
- **Institución:** Universidad Tecnológica de Hermosillo
- **Correo institucional:** a25311035@uthermosillo.edu.mx
- **GitHub:** https://github.com/AguayoGonzalezEdgarSteven

---

Proyecto académico desarrollado para la materia **Aplicaciones Web**, correspondiente a la práctica **U4S8**.
