# owen-modelos

Modelos que descarga **Owen**, el complemento de QGIS con asistente de IA local. Se publican como
archivos de *Releases*, no dentro del repositorio:

| Release (tag) | Contenido | Dirección que usa Owen |
|---|---|---|
| `modelos-ia` | Modelos ONNX de IA geoespacial (respaldo) | `releases/download/modelos-ia/<clave>.onnx` |
| `dependencias` | Bibliotecas de Python para Windows (Python 3.12 y 3.13) que usa Owen: onnxruntime, PyMuPDF, RapidOCR y lo que necesitan (respaldo) | `releases/download/dependencias/<archivo>.whl` |
| `modelo-v1`, `modelo-v3`… | Modelo de lenguaje de Owen (GGUF) | `releases/download/modelo-v1/copiloto-qgis-1.7b-Q4_K_M.gguf` |

## Lista de modelos (`catalog.json`)
Owen consulta `catalog.json` de este repositorio para saber qué modelos de lenguaje hay disponibles. Al publicar
un modelo nuevo (por ejemplo Owen v3), agrega aquí su entrada con su dirección y su SHA-256: todos los usuarios
lo verán en «Modelo… → Buscar modelos nuevos» sin actualizar el complemento.

## Respaldo de modelos de IA geoespacial
Owen busca cada modelo primero en la release `modelos-ia` y, si no está, en el sitio original de sus
autores. Solo se respaldan los modelos cuya licencia permite redistribuirlos; ver `LICENCIAS.md`.

| Clave | Modelo | Autores | ¿En el respaldo? |
|---|---|---|---|
| barcos | Ship Detection (YOLOv8s) | Artur Woźniak | Sí (AGPL-3.0) |
| arboles, autos, aviones, tanques, edificios, cobertura, cobertura_sentinel2, caminos | Deepness Model Zoo | PUT Vision | Pendiente de permiso |

Catálogo original: [Deepness Model Zoo](https://qgis-plugin-deepness.readthedocs.io/en/latest/main/main_model_zoo.html).

## Bibliotecas de Python (release `dependencias`)

Owen instala en el Python de QGIS (para el usuario, sin administrador) tres bibliotecas que QGIS no trae:
**onnxruntime** (modelos de IA), **PyMuPDF** (leer cartas en PDF) y **RapidOCR** (leer el texto de leyendas
y márgenes). Primero descarga las ruedas (`.whl`) de esta release y las instala sin conexión a PyPI; si
la release no responde o no hay rueda para su versión de Python, usa PyPI. En ambos casos **nunca cambia
numpy** (el de QGIS). Son copias sin modificar de las publicadas en PyPI; sus licencias están en
`LICENCIAS.md`.
