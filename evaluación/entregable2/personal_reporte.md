# Entregable 2 - Documentación

## Criterios de exclusión de ejemplos

1. Se eliminan los ejemplos que tengan valores mayores al:
   - $98\%$ de los datos para `Price`.
   - $99\%$ de los datos para `Bedroom2`.
   - $99\%$ de los datos para `Car`.
   - $99\%$ de los datos para `Landsize`.
   - $98\%$ de los datos para `BuildingArea`.
2. Se eliminan los ejemplos que tengan valores menores a:
   - $10$ para `BuildingArea`.

## Características seleccionadas

- *Categóricas* -> se codifican con *One-Hot* sin reducción de categorías:
  - `Type`: tipo de propiedad (h: casa, u: departamento, t: casa adosada).
  - `Regionname`: región de Melbourne.
- *Numéricas*
  - `Price`: precio de la propiedad.
  - `Bedroom2`: cantidad de dormitorios.
  - `Rooms`: cantidad de habitaciones.
  - `Car`: cantidad de cocheras.
  - `Landsize`: tamaño del terreno.
  - `YearBuilt`: año de construcción.
  - `BuildingArea`: tamaño de la construcción.

## Transformaciones e imputaciones realizadas
- Se imputa `YearBuilt` con KNN realizando una *normalización* a los datos con *QuantileTransformer* (luego se invierte para obtener los datos originales).
- Se imputa `BuildingArea` con KNN realizando un *escalado* a los datos con *StandardScaler* (luego se invierte para obtener los datos originales).

## Datos aumentados
- Se aumentan los datos con PCA para obtener las primeras dos componentes principales de los datos imputados por KNN.