# Análisis de delitos violentos en Uruguay (2013–2024)

Este repositorio contiene un script en R con el objetivo de realizar un análisis descriptivo y territorial de la evolución de homicidios, rapiñas y violencia doméstica en Uruguay entre 2013 y 2024, utilizando datos oficiales del Ministerio del Interior y del Instituto Nacional de Estadística.

---

## Hallazgos principales

- Las **rapiñas** alcanzaron su pico en 2019 con 30.640 casos y se redujeron fuertemente hasta 2024, llegando a niveles similares a los de 2013. Su concentración territorial es marcada: Montevideo, Canelones y San José concentran las tasas más altas durante todo el período.
- Los **homicidios** tuvieron su máximo en 2018 con 420 casos. Luego de una reducción, se estabilizaron en valores algo inferiores al pico entre 2022 y 2024. Departamentos fronterizos con Brasil como Rivera, Artigas y Cerro Largo presentan incrementos pronunciados en ciertos períodos.
- La **violencia doméstica** muestra un crecimiento lento pero sostenido a lo largo de todo el período, pasando de 26.288 casos en 2013 a 40.352 en 2023. A diferencia de los otros delitos, su distribución es más homogénea a nivel nacional, con tasas altas consistentes en Salto, Paysandú y Lavalleja.
- Montevideo presenta la **tasa más baja de violencia doméstica** entre todos los departamentos, lo que puede vincularse tanto a una mayor cultura de denuncia como a diferencias en el acceso a servicios institucionales respecto al interior del país.

---

## Contenido del repositorio

- `Script_analisis.R` — script principal con todo el flujo de trabajo: carga y limpieza de datos, transformación y agregación, cálculo de indicadores, y generación de gráficos y mapas.
- `/gifs` — material audiovisual complementario con la evolución departamental año a año de cada delito.

---

## Paquetes utilizados

- `sf`
- `readr`
- `readxl`
- `tidyverse`

---

## Fuentes de datos

| Dato | Fuente |
|---|---|
| Homicidios dolosos consumados | Observatorio Nacional sobre Violencia y Criminalidad – Ministerio del Interior |
| Denuncias de otros delitos (rapiñas y violencia doméstica) | Observatorio Nacional sobre Violencia y Criminalidad – Ministerio del Interior |
| Población departamental | Instituto Nacional de Estadística (INE) – Estimaciones y proyecciones |
| Cartografía departamental | Leandro Vieira (alotropico) – [uruguay.geo](https://github.com/alotropico/uruguay.geo) |

Todos los datos de delitos están disponibles en el [Catálogo de Datos Abiertos del Gobierno de Uruguay](https://catalogodatos.gub.uy/dataset/ministerio-del-interior-delitos_denunciados_en_el_uruguay).

---

## Descripción del análisis

El script realiza las siguientes etapas:

1. Carga de datos desde archivos CSV y XLSX
2. Filtrado y etiquetado de los tres delitos analizados
3. Homogeneización de variables (departamentos, delitos y años)
4. Agregación por departamento y año, completando combinaciones sin casos para evitar ausencias en la serie temporal
5. Cálculo de variaciones anuales por departamento y a nivel nacional
6. Cálculo de tasas departamentales cada 100.000 habitantes con base en proyecciones del INE
7. Identificación de años con valores máximos y mínimos por delito
8. Visualización mediante gráfico de líneas nacional (escala logarítmica) y mapas coropléticos departamentales

---

## Visualizaciones generadas

- Evolución nacional de los tres delitos (2013–2024) en escala logarítmica
- Tasa de homicidios por departamento
- Tasa de violencia doméstica por departamento
- Tasa de rapiñas por departamento

> Cada mapa puede generarse para cualquier año del período modificando el filtro `filter(AÑO == 20xx, ...)` en el script.

---

## Cómo ejecutar el script

1. Clonar el repositorio o descargarlo como ZIP
2. Abrir `Script_analisis.R` en RStudio
3. Ajustar las rutas de los archivos a la ubicación local de los datos
4. Ejecutar el script completo

> El script utiliza rutas locales absolutas que deben modificarse según el entorno del usuario.

---

## Notas metodológicas

El análisis es de carácter descriptivo: busca identificar tendencias y fluctuaciones sin establecer relaciones causales. Los datos provienen de registros administrativos y denuncias oficiales, por lo que los resultados reflejan la violencia registrada por el Estado y no necesariamente su magnitud real. Delitos como la violencia doméstica y las rapiñas presentan niveles de subdenuncia que condicionan la interpretación de los datos.

---

## Autoría

Elaboración propia con base en datos del Ministerio del Interior y el Instituto Nacional de Estadística.
