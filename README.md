# Análisis de Precios de Vivienda en España

## Descripción

Este repositorio contiene un proyecto de análisis de precios de vivienda en España. El objetivo principal es procesar y limpiar datos de valor tasado y compraventa de viviendas, organizándolos por Comunidades Autónomas y Provincias. El notebook `vienda_limpieza.ipynb` detalla el proceso de extracción, transformación y carga (ETL) de los datos.

## Estructura del Repositorio

*   `README.md`: Este archivo.
*   `valor_m2_ccaa.csv`: Archivo CSV resultante del proceso de limpieza, conteniendo el valor del m² por Comunidad Autónoma.
*   `valor_m2_provincias.csv`: Archivo CSV resultante del proceso de limpieza, conteniendo el valor del m² por Provincia.
*   `vienda_limpieza.ipynb`: Notebook de Jupyter que documenta el proceso de limpieza y preprocesamiento de los datos.
*   `files/`: Directorio que contiene los datasets originales utilizados para el análisis:
    *   `Compraventa.csv`: Datos de compraventa de viviendas.
    *   `indice_precios.csv`: Índice de precios de vivienda (posiblemente no usado en el notebook de limpieza, pero presente en la estructura).
    *   `Valor_Tasado.csv`: Datos de valor tasado de viviendas.

## Origen de los Datos

Los datos utilizados en este proyecto provienen de diversas fuentes obtenidas de organismos oficiales y portales inmobiliarios, y se centran en métricas relacionadas con el mercado inmobiliario español, como el valor tasado por metro cuadrado y estadísticas de compraventa.

### 🏠 DATASET 1: VALOR TASADO DE VIVIENDA (€/m²)

**¿Qué contiene?**
- Precio medio de tasación de viviendas por comunidad autónoma y provincia
- **7,043 registros** desde **1995 hasta 2022** (27 años)
- Frecuencia: **Trimestral**
- Cobertura: **65 geografías** (17 comunidades autónomas + provincias principales)

**Datos clave:**
- Las zonas más caras históricamente son: **Madrid, Barcelona, País Vasco, Baleares**
- Las más económicas: **Extremadura, Castilla-La Mancha, provincias del interior**
- Rango de precios: desde ~300 €/m² hasta más de 3,000 €/m² en zonas premium
- Permite ver la **burbuja inmobiliaria de 2008** y la recuperación posterior

---

### 📈 DATASET 2: ÍNDICES Y TASAS DE VARIACIÓN DE PRECIOS

**¿Qué contiene?**
- Variaciones porcentuales de precios (IPV - Índice de Precios de Vivienda del INE)
- Datos desde **2007 hasta 2025** (trimestral)
- Incluye variaciones: **trimestral, anual, interanual**

**Tipos de vivienda:**
- Vivienda nueva
- Vivienda de segunda mano
- Total (agregado)

**Utilidad:**
- Ver **tendencias de crecimiento/caída** de precios
- Identificar **ciclos del mercado inmobiliario**
- Comparar comportamiento de vivienda nueva vs usada

---

### 🔑 DATASET 3: COMPRAVENTA TRIMESTRAL DE VIVIENDAS

**¿Qué contiene?**
- Número de transacciones de compraventa de viviendas
- Datos desde **2007 hasta 2025** (trimestral)
- Desglose por: **comunidad autónoma, provincia, tipo de vivienda**

**Categorías:**
- Vivienda libre vs protegida
- Vivienda nueva vs usada
- Total de transacciones

**Datos clave:**
- Millones de transacciones históricas
- Permite ver el **volumen del mercado** y su evolución
- Identifica zonas con mayor **dinamismo comercial**

## Proceso de Limpieza y Transformación (ETL)

El notebook `vienda_limpieza.ipynb` realiza las siguientes operaciones principales:

1.  **Carga de Datos**: Importa los datasets `Valor_Tasado.csv` y `Compraventa.csv` utilizando la librería `pandas`.
2.  **Normalización de Nombres**: Limpia y estandariza los nombres de las Comunidades Autónomas y Provincias para asegurar consistencia entre los diferentes datasets.
3.  **Filtrado y Separación**: Separa los datos procesados en dos archivos CSV distintos: uno para las Comunidades Autónomas (`valor_m2_ccaa.csv`) y otro para las Provincias (`valor_m2_provincias.csv`).

## Cómo Utilizar

1.  Clona este repositorio:
    ```bash
    git clone https://github.com/tu_usuario/analisis-precios-vivienda-espa-a.git
    cd analisis-precios-vivienda-espa-a
    ```
2.  Abre el notebook `vienda_limpieza.ipynb` en un entorno Jupyter (JupyterLab, Jupyter Notebook, VS Code con extensión Python):
    ```bash
    jupyter notebook vienda_limpieza.ipynb
    ```
3.  Ejecuta las celdas del notebook para replicar el proceso de limpieza de datos y generar los archivos CSV resultantes.

## Proximos Pasos

Se está realizando un dashboard interactivo utilizando `Power BI` para visualizar los precios de vivienda por Comunidad Autónoma y Provincia, permitiendo a los usuarios explorar las tendencias históricas y comparar diferentes regiones.

## Contribuciones

Si deseas contribuir a este proyecto, por favor, abre un "issue" o envía un "pull request".

