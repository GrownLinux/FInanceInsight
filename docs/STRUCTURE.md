# Estructura del Proyecto FinanceInsight

## Visión General

FinanceInsight está organizado en varios módulos Django y una aplicación frontend React. Aquí está la estructura general del proyecto:

```
financeinsight/
├── api/
├── core/
├── users/
├── analysis/
├── reports/
├── frontend/
├── docs/
└── manage.py
```

## Descripción de los Módulos

### api/
Contiene la configuración y vistas para la API REST.

- `views.py`: Vistas de la API
- `serializers.py`: Serializadores para los modelos
- `urls.py`: Configuración de URLs para la API

### core/
Módulo central del proyecto, contiene configuraciones y utilidades compartidas.

- `settings.py`: Configuraciones de Django
- `celery.py`: Configuración de Celery
- `utils.py`: Funciones de utilidad compartidas

### users/
Maneja la autenticación y gestión de usuarios.

- `models.py`: Modelo de usuario personalizado
- `views.py`: Vistas relacionadas con usuarios
- `forms.py`: Formularios para registro y perfil de usuario

### analysis/
Contiene la lógica para el análisis financiero.

- `models.py`: Modelos para datos financieros
- `services.py`: Servicios de análisis financiero
- `tasks.py`: Tareas de Celery para análisis en segundo plano

### reports/
Maneja la generación y gestión de informes.

- `models.py`: Modelos para informes
- `views.py`: Vistas para generación de informes
- `templates/`: Plantillas para informes PDF

### frontend/
Aplicación React para la interfaz de usuario.

- `src/`: Código fuente de React
  - `components/`: Componentes React reutilizables
  - `pages/`: Componentes de página principales
  - `services/`: Servicios para comunicación con la API
- `public/`: Archivos estáticos públicos

### docs/
Documentación del proyecto.

- `INSTALL.md`: Guía de instalación
- `USER_GUIDE.md`: Guía de usuario
- `API_DOCS.md`: Documentación de la API
- `CONTRIBUTING.md`: Guía para contribuidores

### manage.py
Script de gestión de Django para comandos administrativos.

## Flujo de Datos

1. Las solicitudes llegan a través de `api/urls.py`.
2. `api/views.py` procesa las solicitudes y se comunica con los módulos correspondientes.
3. Los módulos (`analysis`, `reports`, etc.) realizan la lógica de negocio.
4. Los resultados se serializan y se devuelven al frontend.
5. La aplicación React en `frontend/` renderiza los datos para el usuario.

## Consideraciones de Desarrollo

- Mantén la lógica de negocio en los módulos específicos (`analysis`, `reports`, etc.).
- Utiliza `core/utils.py` para funciones compartidas entre módulos.
- Sigue las convenciones de nomenclatura de Django y React.
- Documenta las funciones y clases principales para facilitar el mantenimiento.

Para más detalles sobre cómo contribuir al proyecto, consulta [CONTRIBUTING.md](CONTRIBUTING.md).