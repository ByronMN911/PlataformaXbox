Este proyecto es una plataforma de e-commerce moderna desarrollada para las materias de Ambientes Computacionales y Calidad de Software. Se basa en una arquitectura desacoplada con un backend robusto en Django y un frontend dinámico en Angular.

* Tecnologías Utilizadas
Backend: Django 6.0.3 & Django REST Framework (DRF).

Frontend: Angular 21.2.0 (SPA) & Bootstrap 5.3.

Base de Datos: PostgreSQL.

Autenticación: JSON Web Tokens (JWT).

* Guía de Configuración Inicial
Sigue estos pasos exactamente para tener el entorno de desarrollo listo en tu máquina local.

1. Clonación del Repositorio

git clone https://github.com/tu-usuario/tu-repositorio.git
cd tu-repositorio

2. Configuración del Backend (Python/Django)
Entra en la carpeta del backend, crea tu entorno virtual e instala las dependencias:
cd backend
python -m venv venv

# En Windows:
venv\Scripts\activate

# Instalar librerías
pip install -r requirements.txt

* Configuración de Variables de Entorno
Crea un archivo llamado .env dentro de la carpeta backend/ y configura tus credenciales de PostgreSQL:

SECRET_KEY=tu_clave_secreta_aqui
DEBUG=True
DATABASE_URL=postgres://tu_usuario:tu_password@localhost:5432/tuti_db

3. Preparación de la Base de Datos
Asegúrate de que PostgreSQL esté corriendo y que hayas creado la base de datos tuti_db. Luego ejecuta:

# Crear estructura de tablas
python manage.py migrate

# CARGAR DATOS INICIALES (Productos y Categorías de Byron)
python manage.py loaddata datos_iniciales.json

# Crear tu propio acceso de administrador
python manage.py createsuperuser
puedes acceder al panel del administrador yendo a http://127.0.0.1:8000/admin/

4. Configuración del Frontend (Angular)
Abre una nueva terminal en la raíz del proyecto:
cd frontend
npm install

* Cómo ejecutar el proyecto
Para ver el sistema en funcionamiento, debes tener ambas terminales corriendo:

Backend: python manage.py runserver (Corre en http://127.0.0.1:8000)

Frontend: ng serve o npm start (Corre en http://localhost:4200)

* Flujo de Trabajo con Git (Ramas)
Para mantener la Calidad del Software, no trabajaremos directamente en main.

Crea una rama para tu tarea: git checkout -b feature/nombre-tarea.

Sube tus cambios: git push origin feature/nombre-tarea.

Abre un Pull Request en GitHub para revisión.

* Notas de Arquitectura
Importante: La comunicación entre Angular y Django se realiza a través de una API REST protegida. 
El catálogo de productos está disponible en el endpoint /api/productos/.