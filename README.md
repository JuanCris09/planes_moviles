# 📊 Análisis de Ingresos de Tarifas de Telecomunicaciones (Megaline)

## 📖 Tabla de Contenidos

1.  [🎯 Objetivo del Proyecto](#-objetivo-del-proyecto)
2.  [🛠️ Tecnologías y Librerías Utilizadas](#-tecnologías-y-librerías-utilizadas)
3.  [📁 Estructura del Notebook (Flujo de Trabajo)](#-estructura-del-notebook-flujo-de-trabajo)
4.  [⚙️ Instalación y Requisitos](#-instalación-y-requisitos)
5.  [⭐ Conclusiones (Pendiente)](#-conclusiones-pendiente)
6.  [🤝 Contribuciones y Autor](#-contribuciones-y-autor)

---

## 🎯 Objetivo del Proyecto

El objetivo principal de este proyecto es realizar un **análisis preliminar** del comportamiento de una muestra de clientes de la operadora de telecomunicaciones Megaline (basado en 500 usuarios en 2018) para determinar cuál de sus dos tarifas de prepago, **Surf** o **Ultimate**, genera consistentemente **más ingresos** para la empresa.

Esta información es crucial para el departamento comercial para poder ajustar el presupuesto de publicidad y enfocar los esfuerzos de marketing en la opción más rentable.

## 🛠️ Tecnologías y Librerías Utilizadas

Este análisis fue desarrollado en un entorno de **Jupyter Notebook** (o similar) utilizando la librería fundamental de Python para la ciencia de datos.

* **Lenguaje:** Python 3.x
* **Librerías principales:**
    * `pandas`: Herramienta esencial para la manipulación, limpieza y preparación de los grandes conjuntos de datos (DataFrames).
    * `numpy`: Utilizado para operaciones numéricas eficientes, especialmente en el redondeo de minutos/GB.
    * `matplotlib.pyplot` y `seaborn`: Para la visualización de datos, la exploración estadística y la creación de histogramas de uso.
    * `scipy.stats`: Para realizar pruebas de hipótesis estadísticas (como la prueba t de Student) con el fin de validar si las diferencias de ingresos observadas son estadísticamente significativas.


## 📁 Estructura del Notebook (Flujo de Trabajo)

El proceso de análisis está dividido en las siguientes etapas clave:

1.  **Carga de Datos:** Importación de los cinco archivos CSV.
2.  **Preparación de Datos:**
    * Inspección inicial y corrección de tipos de datos, con especial énfasis en la conversión de las columnas de fecha (ej. `reg_date`, `call_date`) a formato `datetime`.
    * Ajuste de las reglas de redondeo de Megaline (redondeo de minutos y GB consumidos al alza por mes).
3.  **Cálculo de Consumo Mensual:** Agrupación y resumen del uso mensual (llamadas, mensajes, internet) por cada usuario.
4.  **Cálculo de Ingresos:** Fusión de las tablas de uso y las tablas de tarifas para calcular el ingreso total generado por cada usuario, sumando el pago mensual fijo y los cargos por uso excedente.
5.  **Análisis de Datos y Estadísticas:** Estudio descriptivo y visualización de las distribuciones de consumo e ingresos por cada tarifa.
6.  **Pruebas de Hipótesis:** Realización de pruebas estadísticas para comparar los ingresos medios entre tarifas y entre diferentes grupos geográficos.

## ⚙️ Instalación y Requisitos

Para ejecutar el código y replicar el análisis:

### 1. Requisitos de Librerías

Asegúrate de que todas las dependencias de Python listadas anteriormente estén instaladas en tu entorno:

```bash
pip install pandas numpy matplotlib seaborn scipy
```
El análisis requiere que los siguientes archivos CSV estén disponibles en la ruta especificada por el proyecto (/datasets/):
```
megaline_calls.csv

megaline_internet.csv

megaline_messages.csv

megaline_plans.csv

megaline_users.csv
```
## ⭐ Conclusiones
Analizando entre los dos planes ambos tienen la capaciadad de vender el servicio, que es lo que pasa con el plan ultimate tiene una estabilidad,
los clientes tienden usar todos los servicios como los mensajes, llamadas pero el tema de internet casi no llega al limite, en cuanto el plan surf
veo que hay mas frecuencia en cada uno de los servicios, cabe resaltar que son algunos clientes que llegan a superar los limites del plan. Aun asi haciendo comparaciones,
de diferentes planes existen la diferencia estadisticamente significativa, es decir que puede existir efectos o cambios respecto los ingresos promedios.

## 🤝 Contribuciones y Autor
Autor: Juan Cristancho

Contribuciones: Las sugerencias y mejoras para optimizar el análisis o la visualización son bienvenidas.
