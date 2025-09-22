# Solución de Problemas — Regresión Logística y Validación Cruzada

## Descripción del análisis
El objetivo principal fue modelar el nivel de **adicción al teléfono** de los estudiantes a partir de variables relacionadas con su tiempo de uso y características personales.  
Se construyó un modelo de **regresión logística**, evaluado con validación cruzada y métricas de desempeño, y se interpretaron los coeficientes para identificar los factores más influyentes.

## Variables incluidas
- **Variables de uso**: tiempo en redes sociales, horas de uso diario, tiempo en videojuegos, número de aplicaciones usadas, etc.  
- **Variables personales**: edad, horas de sueño, autoestima, desempeño académico, comunicación familiar, entre otras.  
- **Variable dependiente (binaria)**:  
  - 0 → nivel bajo de adicción (≤ mediana)  
  - 1 → nivel alto de adicción (> mediana)  

## Pasos realizados

1. **Binarización de la variable objetivo**  
   Se transformó `Addiction_Level` en una variable binaria (alta/baja adicción) usando la mediana como umbral.

2. **División en conjuntos**  
   Se realizó un split 80/20 estratificado, garantizando el balance de clases en entrenamiento y prueba.

3. **Validación cruzada**  
   Se entrenó el modelo de regresión logística con el conjunto de entrenamiento y se aplicó validación cruzada estratificada con 5 folds, obteniendo una exactitud promedio de ~94%.

4. **Evaluación en prueba con distintos umbrales**  
   Se evaluó el modelo en el conjunto de prueba bajo tres umbrales (0.5, 0.7 y 0.3), mostrando cómo cambia el balance entre sensibilidad y especificidad.

5. **Curva ROC y AUC**  
   Se graficó la curva ROC, obteniendo un **AUC de 0.979**, lo que confirma un excelente poder de discriminación del modelo.

6. **Interpretación de coeficientes**  
   - Factores de riesgo (coeficientes positivos): tiempo en redes sociales, horas de uso diario y tiempo en videojuegos.  
   - Factores protectores (coeficientes negativos): más horas de sueño, mayor edad y autoestima.  

## Conclusión
El modelo de **regresión logística** mostró un desempeño sobresaliente, con alta exactitud y un AUC cercano a 1.  
Además de su capacidad predictiva, permitió identificar variables clave asociadas a la adicción al teléfono: el **tiempo frente a pantallas** incrementa el riesgo, mientras que **sueño, edad y autoestima** reducen la probabilidad de adicción.

## Archivos generados
- [Notebook en Jupyter](Prediccion_Adiccion_Telefono.ipynb)  
- [Versión en HTML](Prediccion_Adiccion_Telefono.html)  
- [Base de datos](teen_phone_addiction_dataset.csv)  
