# Guía de Instalación de FinanceInsight

## Requisitos Previos

Antes de comenzar, asegúrate de tener instalado:

- Python 3.9+
- PostgreSQL 13+
- Node.js 14+
- Git

## Pasos de Instalación

1. Clonar el repositorio:
   ```
   git clone https://github.com/tu-organizacion/financeinsight.git
   cd financeinsight
   ```

2. Configurar el entorno virtual de Python:
   ```
   python -m venv venv
   source venv/bin/activate  # En Windows: venv\Scripts\activate
   ```

3. Instalar dependencias de Python:
   ```
   pip install -r requirements.txt
   ```

4. Configurar la base de datos:
   - Crea una base de datos PostgreSQL para el proyecto
   - Copia el archivo `.env.example` a `.env` y actualiza las variables de entorno

5. Aplicar migraciones:
   ```
   python manage.py migrate
   ```

6. Instalar dependencias de frontend:
   ```
   cd frontend
   npm install
   ```

7. Compilar assets de frontend:
   ```
   npm run build
   ```

8. Volver al directorio raíz y iniciar el servidor:
   ```
   cd ..
   python manage.py runserver
   ```

9. Visita `http://localhost:8000` en tu navegador para ver la aplicación.

## Configuración Adicional

- Para configurar Celery y Redis, consulta la sección correspondiente en nuestra [guía de configuración de desarrollo](DEV_SETUP.md).
- Para configurar el entorno de producción, consulta nuestra [guía de despliegue](DEPLOY.md).

Si encuentras algún problema durante la instalación, por favor consulta nuestra [sección de solución de problemas](TROUBLESHOOTING.md) o abre un issue en GitHub.