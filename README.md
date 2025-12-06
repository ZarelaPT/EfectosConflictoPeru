# EfectosConflictoPeru
Proyecto final - Estadística para el análisis político 2 (PUCP)

🔗 Link del dashboard (GitHub Pages): https://zarelapt.github.io/EfectosConflictoPeru/  

Este dashboard fue construido en RMarkdown (flexdashboard) y se publica utilizando GitHub Pages, cumpliendo el requisito del curso para la entrega del proyecto final.

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

## 📂 **Estructura del repositorio** 

EfectosConflictoPeru/
│
├── README.md
├── .gitignore
│
├── data/
│   ├── censos.csv
│   ├── intervenciones_CVR.csv
│   ├── victimas_CVR.csv
│   └── base_unificada.csv
│
├── scripts/
│   └── limpieza.Rmd

---

## 🧹 **Proceso de limpieza**

Se realizó:

- Estandarización de nombres (`clean_names()`)
- Conversión de strings numéricos a números
- Filtrado de 6 departamentos relevantes
- Conversión de etiquetas SPSS
- Conteo de víctimas (mue_des_est)  
- Conteo de intervenciones (actos_est)
- Unión final de las 3 bases

---

# 🧩 **Diccionario de datos (formal)**

### **Diccionario de datos – Base unificada**

Esta base de datos contiene las siguientes variables:

| Variable | Tipo | Fuente | Definición |
|---------|------|---------|------------|
| **departamentos** | Factor | Censos / CVR | Departamento del Perú incluido en el análisis. |
| **total_1993** | Numérico | INEI Censo 1993 | Población total registrada en el censo 1993. |
| **urbana_1993** | Numérico | INEI Censo 1993 | Población urbana 1993. |
| **rural_1993** | Numérico | INEI Censo 1993 | Población rural 1993. |
| **total_2017** | Numérico | INEI Censo 2017 | Población total registrada en 2017. |
| **urbana_2017** | Numérico | INEI Censo 2017 | Población urbana 2017. |
| **rural_2017** | Numérico | INEI Censo 2017 | Población rural 2017. |
| **disminucion_rural** | Numérico | Elaboración propia | Variación porcentual de población rural entre 1993 y 2017. |
| **intervenciones_CVR** | Numérico | CVR – ACTOS_EST | Número de eventos del conflicto en cada departamento. |
| **victimas_CVR** | Numérico | CVR – MUE_DES_EST | Número total de víctimas declaradas al CVR. |
| **rural_prop_1993** | Numérico | Elaboración propia | Proporción rural 1993 = rural_1993 / total_1993. |
| **rural_prop_2017** | Numérico | Elaboración propia | Proporción rural 2017 = rural_2017 / total_2017. |

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





