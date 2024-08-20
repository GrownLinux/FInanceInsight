# Configuración del Entorno de Desarrollo para FinanceInsight

## Requisitos

- Python 3.9+
- PostgreSQL 13+
- Node.js 14+
- Redis (para Celery)
- Git

## Configuración del Entorno

1. Clona el repositorio:
   ```
   git clone https://github.com/tu-organizacion/financeinsight.git
   cd financeinsight
   ```

2. Crea y activa un entorno virtual:
   ```
   python -m venv venv
   source venv/bin/activate  # En Windows: venv\Scripts\activate
   ```

3. Instala las dependencias de Python:
   ```
   pip install -r requirements.txt
   ```

4. Configura las variables de entorno:
   - Copia `.env.example` a `.env`
   - Edita `.env` con tus configuraciones locales

5. Configura la base de datos:
   - Crea una base de datos PostgreSQL para el proyecto
   - Actualiza las credenciales de la base de datos en `.env`

6. Aplica las migraciones:
   ```
   python manage.py migrate
   ```

7. Instala las dependencias de frontend:
   ```
   cd frontend
   npm install
   ```

## Configuración de Celery

1. Asegúrate de que Redis esté instalado y funcionando.

2. En una nueva terminal, inicia el worker de Celery:
   ```
   celery -A financeinsight worker -l info
   ```

## Ejecutar el Proyecto

1. En una terminal, inicia el servidor de Django:
   ```
   python manage.py runserver
   ```

2. En otra terminal, inicia el servidor de desarrollo de React:
   ```
   cd frontend
   npm start
   ```

3. Visita `http://localhost:3000` en tu navegador.

## Herramientas de Desarrollo Recomendadas

- VSCode con las extensiones Python y ESLint
- pgAdmin para administrar PostgreSQL
- Postman para probar APIs

## Configuración de Pre-commit Hooks

1. Instala pre-commit:
   ```
   pip install pre-commit
   ```

2. Configura los hooks:
   ```
   pre-commit install
   ```

## Ejecutar Pruebas

- Para pruebas de backend:
  ```
  python manage.py test
  ```

- Para pruebas de frontend:
  ```
  cd frontend
  npm test
  ```

## Solución de Problemas Comunes

- Si encuentras problemas con las dependencias, intenta recrear el entorno virtual.
- Para problemas con la base de datos, verifica la conexión y los permisos en PostgreSQL.
- Si Celery no se conecta, asegúrate de que Redis esté funcionando correctamente.

Para más ayuda, consulta nuestra [guía de solución de problemas](TROUBLESHOOTING.md) o contacta al equipo de desarrollo.