# Análisis Comparativo de la Oferta y Capacidad de Alojamiento Turístico en el Eje Cafetero (Risaralda y Armenia)

¿En qué se diferencia la oferta de alojamiento entre Risaralda y Armenia (Quindío), considerando que Risaralda parece apuntar más al turismo de negocios y Armenia al descanso vacacional, y cómo pueden las Secretarías de Turismo de ambas regiones usar esta información para crear campañas que atraigan visitantes en los meses más flojos del año?

---

## Integrantes
- **Christopher Arboleda**
- **Andres Felipe Moreano**
- **Leonardo Trejos**

---

## 🎯 Objetivo del Proyecto
Este proyecto de minería de datos busca analizar y comparar las características, tipologías y capacidad instalada (habitaciones, camas y personal) de los alojamientos formales registrados en el **Registro Nacional de Turismo (RNT)** entre el departamento de **Risaralda** y la ciudad de **Armenia (Quindío)**. 

El propósito es contrastar la vocación de ambas regiones (turismo de negocios/corporativo vs. descanso/vacacional) para que las entidades territoriales de turismo puedan diseñar estrategias y campañas orientadas a mitigar las temporadas bajas.

---

## 📓 Trabajo Realizado en el Notebook (`notebooks/Mineria_Datos.ipynb`)

El notebook contiene el flujo inicial de preparación, estandarización y unificación de datos de las dos fuentes:

1. **Montaje y Carga de Fuentes de Datos:**
   - **Armenia (Quindío):** Carga del dataset (`RNT_Armenia_Quindio.csv`) utilizando codificación `latin1`, gestión dinámica de delimitadores (`;` y `\t`) y limpieza de espacios en encabezados (8.998 registros).
   - **Risaralda:** Carga del dataset (`RNT_Risaralda.csv`) empleando codificación `utf-8-sig` para la correcta lectura de caracteres especiales (ñ, tildes) y eliminación del BOM inicial (16.990 registros).

2. **Estandarización y Homologación de Esquemas:**
   - Mapeo y renombrado de las columnas de Risaralda para hacerlas equivalentes a las de Armenia:
     - `CODIGO_MUNICIPIO` $\rightarrow$ `COD_MUN`
     - `CODIGO_DEPARTAMENTO` $\rightarrow$ `COD_DPTO`
     - `NUMERO_DE_HABITACIONES` $\rightarrow$ `HABITACIONES`
     - `NUMERO_DE_CAMAS` $\rightarrow$ `CAMAS`
     - `NUMERO_DE_EMPLEADOS` $\rightarrow$ `NUM_EMP`
   - Verificación de consistencia de columnas entre ambos conjuntos de datos.

3. **Cruce y Unificación (`df_total`):**
   - Concatenación de ambos datasets en un único DataFrame consolidado con un total de **25.988 registros** y 13 variables comunes.

4. **Diccionario de Datos:**
   - Generación estructurada del diccionario de datos tabular detallando el nombre de cada variable, su tipo de dato (`int64`, `object`), significado y origen de la fuente.

