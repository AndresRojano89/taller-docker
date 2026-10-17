# Gestor de tareas contenerizado

## Integrantes
- Andrés David Rojano Celin 

## Servicios
| Servicio | Tecnología | Función |
|---|---|---|
| frontend | nginx | Página web, puerto 8080; reenvía `/api/` a la API |
| api | Python 3.12 + Flask | API de tareas |
| bd | MySQL 8.4 | Base de datos con volumen `datos-bd` |

## Requisitos
- Docker Desktop abierto (Indicador **Engine running**)
- Git
- Puerto **8080** libre

## Cómo ejecutarlo
1. git clone https://github.com/AndresRojano89/taller-docker.git
2. cd taller-docker
3. Copy-Item .env.example .env
4. docker compose up -d --build
5. Esperar unos 30 segundos, MySQL tarda en arrancar la primera vez y abrir http://localhost:8080
6. Verificar que los tres servicios están en estado Up: docker compose ps

## Cómo detenerlo
-docker compose down

## Problemas frecuentes
| Síntoma | Solución |
|---|---|
| "No fue posible conectar con la API" | Esperar 20–30 segundos y recargar |
| `port is already allocated` | Liberar el 8080: `docker ps` y `docker rm -f NOMBRE`, o `docker compose down` en el otro proyecto |
| Error al descargar imágenes (`no such host`, `timeout`) | Revisar internet, reiniciar Docker Desktop y repetir |
| Cualquier otro error | Revisar `docker compose logs api` y `docker compose logs bd` |