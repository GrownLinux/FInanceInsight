# Flujo de Trabajo de Git en FinanceInsight

Seguimos un flujo de trabajo basado en ramas para mantener nuestro código organizado y facilitar el desarrollo colaborativo.

## Estructura de Ramas

- `main`: Rama principal, contiene el código de producción.
- `develop`: Rama de desarrollo, donde se integran las nuevas características.
- `feature/*`: Ramas para nuevas características o mejoras.
- `hotfix/*`: Ramas para correcciones urgentes en producción.
- `release/*`: Ramas para preparar nuevas versiones para producción.

## Proceso para Nuevas Características

1. Crea una nueva rama desde `develop`:
   ```
   git checkout develop
   git pull origin develop
   git checkout -b feature/nombre-de-tu-caracteristica
   ```

2. Desarrolla tu característica, haciendo commits frecuentes.

3. Cuando la característica esté lista, crea un Pull Request a `develop`.

4. Después de la revisión y aprobación, se hará merge a `develop`.

## Proceso para Hotfixes

1. Crea una rama `hotfix` desde `main`:
   ```
   git checkout main
   git pull origin main
   git checkout -b hotfix/descripcion-del-error
   ```

2. Realiza la corrección y crea un Pull Request tanto a `main` como a `develop`.

## Preparación de Releases

1. Cuando `develop` esté listo para un release, crea una rama `release`:
   ```
   git checkout develop
   git pull origin develop
   git checkout -b release/v1.x.x
   ```

2. Realiza ajustes finales y pruebas.

3. Crea Pull Requests a `main` y `develop`.

## Convenciones de Commit

Usamos [Conventional Commits](https://www.conventionalcommits.org/) para nuestros mensajes de commit:

- `feat:` para nuevas características
- `fix:` para correcciones de errores
- `docs:` para cambios en la documentación
- `style:` para cambios que no afectan el significado del código
- `refactor:` para refactorizaciones de código
- `test:` para añadir o modificar pruebas
- `chore:` para tareas de mantenimiento

Ejemplo: `feat: add company comparison feature`

## Revisión de Código

- Todos los cambios deben ser revisados a través de Pull Requests.
- Asigna al menos un revisor a tu Pull Request.
- Atiende los comentarios y realiza los cambios necesarios.
- El merge solo se puede realizar después de la aprobación y cuando todas las verificaciones automáticas hayan pasado.

Siguiendo este flujo de trabajo, mantenemos un historial de código limpio y facilitamos la colaboración en el equipo.