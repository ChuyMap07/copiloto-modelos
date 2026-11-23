# owen-modelos

Modelos que descarga **Owen**, el complemento de QGIS con asistente de IA local. Se publican como
archivos de *Releases*, no dentro del repositorio:

| Release (tag) | Contenido | Dirección que usa Owen |
|---|---|---|
| `modelos-ia` | Modelos ONNX de IA geoespacial (respaldo) | `releases/download/modelos-ia/<clave>.onnx` |
| `modelo-v1`, `modelo-v3`… | Modelo de lenguaje de Owen (GGUF) | `releases/download/modelo-v1/copiloto-qgis-1.7b-Q4_K_M.gguf` |

## Respaldo de modelos de IA geoespacial
Owen busca cada modelo primero en la release `modelos-ia` y, si no está, en el sitio original de sus
autores. Solo se respaldan los modelos cuya licencia permite redistribuirlos; ver `LICENCIAS.md`.

| Clave | Modelo | Autores | ¿En el respaldo? |
|---|---|---|---|
| barcos | Ship Detection (YOLOv8s) | Artur Woźniak | Sí (AGPL-3.0) |
| arboles, autos, aviones, tanques, edificios, cobertura, cobertura_sentinel2, caminos | Deepness Model Zoo | PUT Vision | Pendiente de permiso |

Catálogo original: [Deepness Model Zoo](https://qgis-plugin-deepness.readthedocs.io/en/latest/main/main_model_zoo.html).
