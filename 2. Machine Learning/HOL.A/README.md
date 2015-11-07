# Aprendizaje Automatizado con Windows Azure
En este laboratorio utilizaremos la suite de aprendizaje automatizado de Azure para crear modelos de clasificación y predicción de datos.

## Paso 1 - Ingresar a la suite de Aprendizaje Automatizado
1. Ingresar a **http://studio.azureml.net/**
1. Logearse con una cuenta de hotmail o outlook
1. Asegurarse de tener seleccionado el "Free-Workspace" <br/>![freews](img/01.jgp)
## Paso 2 - Crear el experimento
1. Hacer click en el botón "New" ubicado en la parte inferior derecha. <br/>![new](img/02.jpg)
2. Seleccionar "Blank Experiment".
## Paso 3 - Diseñar el Experimento
1. En la parte izquierda encontrará el panel de herramientas. <br/>![tools](img/03.jpg)
* Aquí verá todas los elementos que puede arrastrar al Área de Diseño del experimento.
2. Arrastre al experimento el DataSet de ejemplo "Iris Two Class Data" <br/>![data](img/06.jpg)
* Puede probar buscando por el nombre del componente en la parte superior del panel de herramientas.
3. Arrastre al experimento el componente "Split Data", ubicado en la categoria "Data Transformation" -> "Sample and Split" <br/>![split](img/07.jpg)
4. Conecte el nodo de salida del DataSet "Iris Two Class Data" con el nodo de entrada del componente "Split Data". (Los nodos compatibles se iluminarán en color verde).
5. Modifique la propiedad "Fraction of rows in the first output dataset" que inicialmente se encuentra en 0.5 a 0.8, esto indica que la división del conjunto de datos será de 80% para la primera salida y de 20% para la segunda salida.
6. Arrastre al área de diseño el componente "Train Model"
* Conecte el nodo de salida izquierdo del componente "Split Data" al nodo de entrada derecho del componente "Train Model". 
* En el panel de propiedades haga click en el boton "Launch column selector"
* Escriba la palabra "Class" en el campo de texto de la ventana emergente.
* Finalice haciendo click en el boton "Check" de la parte inferior. <br/>![configtrain](img/04.jpg)
7. Arrastre al área de diseño el componente "Two-Class Neural Network" desde el panel de herramientas ubicado en la categoria "Machine Learning" -> "Initialize Model" -> "Clasification" <br/>![netural](img/05.jpg)
* Conente el nodo de salida del componente "Two-Class Neural Network" al nodo de entrada izquierdo del componente "Train Model".
7. Arrastre al área de diseño el componente "Score Model" ubicado en la categoria "Machine Learning" -> "Score".
* Conecte el nodo de salida del componente "Train Model" al nodo de entrada izquierdo del componente "Score Model".
* Conecte el nodo de salida derecho del componte "Split Data" al nodo de entrada derecho del componente "Scorte Model".

### Resultado del Ejercicio
</br>![result](img/08.jpg)