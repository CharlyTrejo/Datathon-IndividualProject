# Machine Learning Datathon-Individual Project
Proyecto realizado por : Carlos Alberto Trejo Rodríguez 

Este Datathon tuvo como objetivo crear un modelo de Mahcine Learning para predecir si el costo de renta de inmuebles en EEUU era baja.
Para ello recibimos dos archivos tipo parquet con cerca de 800,000 registros de anuncios de inmuebles para renta en todo EEUU. 

El archivo train.parquet fue destinado al entrenamiento y evaluación del modelo; mientras que el archivo test.parquet fue destinado a obtener predicciones para ser enviadas al comité del Datathon para la evaluación de mi modelo. 

## Análisis exploratorio de datos, transformación y limpieza de dataset.
El análisis exploratorio de datos junto con la transformación y limpieza del dataset se encuentra disponible en este [archivo](https://github.com/CharlyTrejo/Datathon-IndividualProject/blob/main/EDA_Transformation_Cleaning.ipynb) , dentro de él exploré registros duplicados, valores nulos, medidas estadísticas, además de preparar los datos según mi modelo de Machine Learning utilizado incluyendo variables dummies. 

## Creación, entrenamiento y evaluación del modelo de Machine Learning
En [ML_Creation_training_testing.ipynb](https://github.com/CharlyTrejo/Datathon-IndividualProject/blob/main/ML_Creation_training_testing.ipynb) , se encuentra la creación, entrenamiento y evaluación de mi modelo. 

Para este Datathon elegí trabajar con un modelo de Machine Learning supervisado de clasificación. 

Específicamente elegí trabajar con el modelo **Hist Gradient Boosting Classifier**, el cual está formado por un conjunto de árboles de decisión individuales, entrenados de forma secuencial, de forma que cada nuevo árbol trata de mejorar los errores de los árboles anteriores y la predicción de una nueva observación se obtiene agregando las predicciones de todos los árboles individuales que forman el modelo. 
Hist Gradient Boosting Classifier es un estimador muy rápido y útil para datasets grandes, además de que este modelo tiene soporte nativo para missing values (NaNs). 



Para la evaluación del modelo , utilicé la métrica **Accuracy** para las propiedades de precio bajo (low) a partir de la matriz de confusión (Confusion Matrix).

$$ Accuracy=\frac{TP+TN}{P+N}$$

siendo $TP$ los verdaderos positivos (las propiedades de precio 'low' que realmente lo son), $TN$ verdaderos negativos (las propiedades que realmente NO son de precio 'low') y $P+N$ población total.

## Predicciones para Datathon
Finalmente en [test_transformation.ipynb](https://github.com/CharlyTrejo/Datathon-IndividualProject/blob/main/test_transformation.ipynb) aplique los mismos cambios a nivel de campos(columnas) al dataset test.parquet para obtener las [predicciones](https://github.com/CharlyTrejo/Datathon-IndividualProject/blob/main/CharlyTrejo.csv) que fueron enviadas al comité del datathon para la evaluación de mi modelo de Machine Learning. 

Aunque las debidas transformaciones del dataset para la predicción del modelo de ML se encuentran en [test_transformation.ipynb](https://github.com/CharlyTrejo/Datathon-IndividualProject/blob/main/test_transformation.ipynb), la predicción se encuentra en otro archivo, en este caso [ML_Creation_training_testing.ipynb](https://github.com/CharlyTrejo/Datathon-IndividualProject/blob/main/ML_Creation_training_testing.ipynb).

