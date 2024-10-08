# Reconocimiento Óptico de Caracteres con Amazon Rekognition

## Índice
1. [Introducción](#introducción)
2. [Requisitos](#requisitos)
3. [Configuración del Entorno](#configuración-del-entorno)
4. [Estructura del Proyecto](#estructura-del-proyecto)
5. [Uso del Código](#uso-del-código)
6. [Funcionalidades Implementadas](#funcionalidades-implementadas)
7. [Ejemplo de Salida](#ejemplo-de-salida)
8. [Consideraciones y Mejoras Futuras](#consideraciones-y-mejoras-futuras)

## 1. Introducción

Este repositorio contiene un notebook de Jupyter que implementa el reconocimiento óptico de caracteres (OCR) utilizando Amazon Rekognition. El proyecto está diseñado para extraer texto de imágenes almacenadas en Amazon S3, proporcionando una solución eficiente y escalable para el procesamiento de texto en imágenes.

## 2. Requisitos

Para utilizar este proyecto, necesitarás:

- Una cuenta de AWS con acceso a Amazon Rekognition y S3
- Python 3.x
- Jupyter Notebook
- Bibliotecas de Python: boto3, dotenv

## 3. Configuración del Entorno

1. Clona este repositorio en tu máquina local.
2. Instala las dependencias necesarias:

    ```bash
    pip install boto3 python-dotenv jupyter

    ```

3. Crea un archivo `.env` con las siguientes variables de entorno:

    ```bash
    access_key_id=XXX
    secret_access_key=XXX
    region=XXX
    bucket=XXX
    ```

4. Carga las variables de entorno desde el archivo `.env`:

    ```bash 
    source .env
    ```

## 4. Estructura del Proyecto

El proyecto consta de un solo notebook de Jupyter:

- `Reconocimiento_Optico_de_Caracteres.ipynb`: Contiene todo el código necesario para la implementación del OCR.

## 5. Uso del Código

1. Abre el notebook `Reconocimiento_Optico_de_Caracteres.ipynb` en Jupyter.
2. Ejecuta las celdas en orden, asegurándote de modificar la variable `bucket` con el nombre de tu bucket de S3.
3. El código procesará la imagen especificada y extraerá el texto contenido en ella.

## 6. Funcionalidades Implementadas

El notebook implementa las siguientes funcionalidades:

1. Carga segura de credenciales de AWS desde un archivo `.env`.
2. Conexión al servicio Amazon Rekognition.
3. Envío de una solicitud para detectar texto en una imagen almacenada en S3.
4. Procesamiento de la respuesta de Rekognition para extraer el texto detectado.
5. Visualización del texto extraído, tanto por líneas como por palabras individuales.

## 7. Ejemplo de Salida

El código produce dos tipos de salida:

1. Texto completo extraído de la imagen, incluyendo todas las líneas y palabras detectadas.
2. Texto filtrado mostrando solo las líneas completas, excluyendo palabras individuales.

Ejemplo de salida filtrada:
La confluencia entre la novela y la filosofía española de principios del
siglo XX es el hilo conductor de este trabajo, que nace del interés por
mostrar una relectura, en clave hermenéutica, del vigor filosófico pre-
sente en la novelística del momento. Dicho período se inaugura con el

## 8. Consideraciones y Mejoras Futuras

- El código actual procesa una sola imagen. Podría ampliarse para procesar múltiples imágenes en lote.
- Se podría implementar un manejo de errores más robusto para casos en que la imagen no contenga texto o no se pueda acceder a ella.
- La integración con otras herramientas de AWS, como Amazon Comprehend, podría permitir un análisis más profundo del texto extraído.
- Considerar la implementación de una interfaz de usuario para facilitar la carga de imágenes y la visualización de resultados.

Para cualquier pregunta o sugerencia, por favor abre un issue en este repositorio.