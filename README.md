# Control de Motor - Node-RED

Proyecto de Node-RED con un dashboard para el control de un motor.

## Contenido del dashboard

- **Imagen:** motor trifásico en SVG con ventilador animado y color según el estado.
- **Botones de control:** MARCHA, PARADA, PARO DE EMERGENCIA y RESET.
- **LEDs de estado:** MARCHA (verde), PARADO (rojo) y FALLA (ámbar intermitente).

## Lógica de control

| Comando     | Condición             | Resultado                 |
|-------------|-----------------------|---------------------------|
| MARCHA      | Motor parado          | Pasa a MARCHA             |
| PARADA      | Motor en marcha       | Pasa a PARADO             |
| EMERGENCIA  | Cualquier estado      | Pasa a EMERGENCIA (bloqueo) |
| RESET       | Motor en emergencia   | Pasa a PARADO             |

La segunda salida del nodo función entrega `true`/`false` para comandar el contactor
(reemplazar el nodo debug por GPIO, Modbus, MQTT, S7, etc.).

## Archivos

- `flows.json`: flujos del proyecto.
- `package.json`: metadatos y dependencias del proyecto.

## Requisitos

- Node-RED 3.x o superior con la función Projects habilitada.
- Paquete `node-red-dashboard`.

## Uso

1. Clonar este repositorio desde Node-RED (Projects → New Project → Clone Repository).
2. Instalar las dependencias que solicite el editor.
3. Hacer Deploy y abrir `http://localhost:1880/ui`.
