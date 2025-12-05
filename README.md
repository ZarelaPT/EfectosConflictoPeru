# EfectosConflictoPeru
Proyecto final - Estadística para el análisis político 2 (PUCP)

# Impacto del Conflicto Armado en la Disminución de la Población Rural (1993–2017)

Este repositorio contiene la base de datos unificada y el script de limpieza utilizados para analizar la relación entre la intensidad del conflicto armado interno y la disminución de la población rural en seis departamentos del Perú entre 1993 y 2017.

Los departamentos incluidos en el análisis son:

- apurímac  
- ayacucho  
- huancavelica  
- lambayeque  
- lima  
- piura  

---

## 📌 Objetivo de la base de datos

El objetivo es construir una base integrada que permita evaluar si la intensidad del conflicto armado está asociada con una mayor reducción de la población rural en departamentos con diferentes niveles de exposición al conflicto.

Para ello, la base unificada combina:

### **1. Datos de los Censos Nacionales del INEI (1993 y 2017)**
- población total  
- población urbana  
- población rural  

### **2. Datos de la Comisión de la Verdad y Reconciliación (CVR)**
- número de intervenciones armadas (ACTOS_DEST)  
- número de víctimas registradas (MUE_DES_EST)  

Estos indicadores permiten construir medidas comparables de ruralidad y conflicto en el periodo 1993–2017.

---

## 📁 Estructura del repositorio
├── data/
│ ├── base_unificada.csv
│ ├── censos.csv
│ ├── intervenciones_CVR.csv
│ ├── victimas_CVR.csv
│
├── scripts/
│ └── limpieza.Rmd # Proceso completo de limpieza
│
└── README.md # Este archivo


---

## 📘 Diccionario de Datos (base_unificada.csv)

La base contiene las siguientes variables:

| Variable              | Descripción                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| departamentos         | Nombre del departamento en minúsculas                                       |
| total_1993            | Población total según Censo 1993                                            |
| urbana_1993           | Población urbana 1993                                                       |
| rural_1993            | Población rural 1993                                                        |
| total_2017            | Población total según Censo 2017                                            |
| urbana_2017           | Población urbana 2017                                                       |
| rural_2017            | Población rural 2017                                                        |
| rural_prop_1993       | Proporción de población rural en 1993 (rural_1993 / total_1993)            |
| rural_prop_2017       | Proporción de población rural en 2017 (rural_2017 / total_2017)            |
| disminucion_rural     | Cambio proporcional de población rural entre 1993 y 2017                   |
| intervenciones_CVR    | Número de intervenciones armadas registradas en ACTOS_DEST                 |
| victimas_CVR          | Número de personas afectadas según MUE_DES_EST                             |

---

## 🔧 Reproducibilidad

Para reproducir el proceso completo de limpieza:

1. Abrir el archivo `scripts/limpieza.Rmd`.  
2. Ejecutar los chunks en orden.  
3. Las tres bases limpias se generan automáticamente:  
   - censos  
   - intervenciones_CVR  
   - victimas_CVR  
4. Finalmente, se construye `data/base_unificada.csv`.





