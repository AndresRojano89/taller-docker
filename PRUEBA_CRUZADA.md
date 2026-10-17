# Prueba cruzada

**Equipo evaluador:** Luisa Rossete
**Repositorio probado:** https://github.com/AndresRojano89/taller-docker

## Resultado
El proyecto encendió correctamente siguiendo el README. Los tres servicios (frontend, api, bd) quedaron en estado Up y la aplicación permitió agregar, completar y eliminar tareas.

## Observaciones del otro equipo
1. Al abrir http://localhost:8080 justo después de `docker compose up`, la página mostró "No fue posible conectar con la API". Funcionó al esperar unos segundos y recargar. El README no explicaba que MySQL tarda en arrancar la primera vez.
2. El puerto 8080 estaba ocupado por su propio proyecto y les salió `port is already allocated`. Sugirieron indicar que el puerto debe estar libre.

## Cambios realizados en el README
- Se agregó la espera de 30 segundos antes de abrir la página.
- Se agregó la sección "Problemas frecuentes" con el puerto ocupado, la conexión con la API y la red al descargar imágenes.