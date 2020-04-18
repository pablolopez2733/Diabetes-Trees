![](./images/itam_logo.png)

M. Sc. Liliana Millán Núñez liliana.millan@itam.mx

### Proyecto 1

Cuentas con un dataset del Instituto Nacional de Diabetes y enfermedades de Riñón de la India pertenecientes a mujeres de al menos 21 años de edad (datos reales) [dataset](https://www.dropbox.com/sh/s62jf0voxx00yoz/AAAXnZX4Kwrt9cTfwsyAxgjra?dl=0).

El objetivo consiste en predecir si una mujer tiene o no diabetes.

El dataset conta de las siguentes 7 variables explicativas:

+ `Pregnancies`: Número de embarazos que ha tenido
+ `Glucose`: Concentración de glucosa proveniente de un estudio
+ `BloodPressure`: Presión diastólica sanguínea  
+ `SkinThickness`: Grueso en milímetros de piel de los triceps
+ `Insulin`: Insulina
+ `BMI`: Índice de masa corporal (peso en kg/(altura en metros)^2)
+ `DiabetesPedigreeFunction`: Función de diabetes.
+ `Age`: Edad en años
+ `Outcome`: Variable *target*, diabetes = 1, no diabetes = 0

**Restricción de negocio:** No puedes tener más de 3% de falsos positivos.

![](./images/pointer.png) Todos tus datos son numéricos.

### Todos los equipos

+ Respuesta de las 5 preguntas de tus datos
+ 5 gráficas que hagan summary de tu EDA
+ En tus algoritmos utiliza como random seed la clave única más pequeña (numéricamente) de tu equipo
+ Define cuál es tu etiqueta positiva y cuál tu etiqueta negativa, qué es TP, FP, TN, FN
+ Define qué métrica de desempeño ocuparás para seleccionar el mejor modelo, justifica
+ Utiliza una partición de 70, 30 para entrenamiento y pruebas respectivamente


#### Preguntas

1. ¿Qué valor de BMI tiene el 75% de tus datos?
2. ¿Qué edad corresponde a la mediana?
3. ¿Cuántos hijos tiene el 75% de las mujeres en el dataset?
4. ¿Cuántas observaciones tienes de diabetes?
5. ¿Cuál es la mediana de número de hijos para mujeres entre 25 años y 35 años de edad (inclusive)?


```
np.random.seed(200412)

9,5,3,6,4,8,1,2,7
```

### Árbol

Equipos: 9,5,3,6

+ Utiliza un *k-fold cross validation* de 10
+ Genera un `GridSearch` modificando al menos dos hiperparámetros del árbol con al menos 2 valores diferentes (cada hiperparámetro)
+ Una vez que seleccionaste el mejor modelo, obtén la importancia de variables
+ Selecciona las variables más importantes -> define a partir de qué porcentaje es para ti "más importante" (justifica)
+ Genera un nuevo modelo con *k-fold cross validation* de 10 con las variables seleccionadas en el punto anterior
+ Genera un nuevo `GridSearch` modificando al menos dos hiperparámetros del árbol con al menos 2 valores diferentes (cada hiperparámetro)
+ Una vez que seleccionaste el mejor modelo, obtén la importancia de variables indicando su porcentaje
+ Genera la tabla de métricas
+ Selecciona el mejor punto de threshold de acuerdo a la métrica seleccionada y las restricciones de negocio
+ Genera la matriz de confusión correspondiente a ese punto de corte
+ Genera ROC y AUC


### Random Forest

Equipos: 4,8,1,2,7

+ Utiliza un *k-fold cross validation* de 3
+ Utiliza un `GridSearch` modificando al menos dos hiperparámetros del RF con al menos 2 valores diferentes (cada hiperparámetro), uno de ellos debe ser el número de árboles
+ Una vez que seleccionaste el mejor modelo, obtén la importancia de variables
+ Selecciona las variables más importantes -> define a partir de qué porcentaje es para ti "más importante" (justifica)
+ Genera un nuevo modelo con *k-fold cross validation* de 3 con las variables seleccionadas en el punto anterior
+ Genera un nuevo `GridSearch` modificando al menos dos hiperparámetros del RF con al menos 2 valores diferentes (cada hiperparámetro), uno de ellos debe ser el número de árboles
+ Una vez que seleccionaste el mejor modelo, obtén la importancia de variables indicando su porcentaje
+ Genera la tabla de métricas
+ Selecciona el mejor punto de threshold de acuerdo a la métrica seleccionada y las restricciones de negocio
+ Genera la matriz de confusión correspondiente a ese punto de corte
+ Genera ROC y AUC


### Qué se entrega

+ Un notebook que incluye todo el código generado y texto de explicación para las partes necesarias.
+ Se entrega el **27 de abril 2020** máximo a las **23:59:59 CST** por **correo** a la cuenta: `liliana.millan@itam.mx` con el *subject* `md_ene_20`, **3 puntos menos por cada día de retraso**.
+ El proyecto se hace en equipos de **máximo 2 personas**, solo 1 equipo puede ser de **3 personas**.


### Qué se califica

+ Respuesta de las preguntas
+ EDA
  + 5 gráficas "adecuadas" de acuerdo a lo que quieres expresar, 1 de ellas debe ser un `boxplot`.
  + Cuentan con interpretación
  + Los ejes tienen nombre de la variable y unidad en la que se encuentran (if any)
  + Los ejes incluyen comas para cantidades qeu lo requieran
  + Tienen título
+ Algoritmos
  + Definiste etiqueta positiva y negativa
  + Definiste TP, FP, TN y FN
  + Definiste la métrica de desempeño y justificaste
  + Hiciste la partición "correcta" a *train/test*
  + No hiciste *data leaking*
  + Ocupaste el *random seed* correcto para poder reproducir tus resultados
  + Modificaste los hiperparámetros indicados
  + Indicas los hiperparámetros del mejor modelo
  + Indicas el *threshold* y su implementación para producción.
  + Calculas la matriz de confusión con el *threshold* seleccionado
  + Generas la tabla de métricas
  + Indicas para tu punto de corte el TPR, FPR, TNR, FNR, Precision, Recall y F1-score asociadas
  + Generas ROC y AUC
  + Ocupaste CV de 10 para árboles y 3 para RF
  + Hiciste selección de variables
  + Ocupaste `GridSearch`
  + Seleccionaste las "mejores" variables después de la primera selección de mejor modelo indicando el % de importancia
  + Justificaste tu selección de variables
