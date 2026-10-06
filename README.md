# analysis-connectatel

# ConnectaTel — Análisis de uso de servicios móviles

## Objetivo del proyecto

Este proyecto analiza el comportamiento de uso de los clientes de **ConnectaTel**, una empresa de telecomunicaciones con operaciones en México y Colombia.

El objetivo principal es identificar patrones de uso de llamadas y mensajes, detectar comportamientos atípicos y segmentar a los clientes según su edad y nivel de uso. A partir de este análisis se generan insights que pueden apoyar decisiones comerciales relacionadas con la oferta de planes y la experiencia del cliente.

## Datasets utilizados

El análisis utiliza tres archivos CSV:

- `plans.csv`: información de los planes disponibles, incluyendo precio, minutos incluidos, GB incluidos y costos por consumo adicional.
- `users_latam.csv`: información de los clientes, como edad, ciudad, fecha de registro, plan contratado y fecha de baja.
- `usage.csv`: registros de uso real de los clientes, incluyendo llamadas, duración de llamadas, mensajes y longitud de mensajes.

## Etapas del análisis

El proyecto se desarrolló en las siguientes etapas:

1. **Exploración inicial de los datos**
   - Revisión de dimensiones de los datasets.
   - Identificación de tipos de datos.
   - Inspección de valores nulos e inconsistencias.

2. **Detección de problemas de calidad**
   - Revisión de valores faltantes.
   - Identificación de valores inválidos y sentinels.
   - Revisión y estandarización de fechas.

3. **Limpieza de datos**
   - Reemplazo del valor sentinel `-999` en la columna `age`.
   - Conversión de valores `"?"` en `city` a valores nulos.
   - Corrección y validación de fechas.
   - Conservación justificada de valores nulos en `duration` y `length` según el tipo de registro.

4. **Resumen de uso por usuario**
   - Cantidad total de mensajes.
   - Cantidad total de llamadas.
   - Total de minutos de llamadas.
   - Integración de estas métricas con la información de cada cliente.

5. **Análisis descriptivo y visualización**
   - Distribución de edades.
   - Distribución de mensajes.
   - Distribución de llamadas.
   - Distribución de minutos de llamadas.
   - Comparación entre los planes Básico y Premium.

6. **Detección de outliers**
   - Visualización mediante boxplots.
   - Identificación de valores atípicos con el método IQR.
   - Evaluación de si los outliers corresponden a errores o a clientes con consumo elevado.

7. **Segmentación de clientes**
   - Segmentación por edad.
   - Segmentación por nivel de uso:
     - Bajo uso.
     - Uso medio.
     - Alto uso.

8. **Generación de insights ejecutivos**
   - Identificación de segmentos relevantes.
   - Interpretación de patrones de consumo.
   - Detección de oportunidades comerciales.
   - Recomendaciones para mejorar la oferta de planes.

## Cómo ejecutar el notebook

La forma más sencilla de ejecutar el proyecto es usando **Google Colab**.

1. Abrir [Google Colab](https://colab.research.google.com/).
2. Subir el archivo `.ipynb` del proyecto.
3. Subir también los datasets:
   - `plans.csv`
   - `users_latam.csv`
   - `usage.csv`
4. Verificar que las rutas de lectura de los archivos coincidan con la ubicación donde fueron cargados.
5. Ejecutar las celdas del notebook en orden, desde la primera hasta la última.

El proyecto también puede ejecutarse en Jupyter Notebook o JupyterLab.

## Guía de reproducción

Para reproducir el análisis:

1. Clonar o descargar este repositorio.
2. Colocar el notebook y los datasets en el mismo entorno de trabajo.
3. Instalar las librerías necesarias:

```bash
pip install pandas numpy matplotlib seaborn
