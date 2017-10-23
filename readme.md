ANGULAR 111: APP, CONTROLLERS Y SCOPE

	DIRECTIVAS App Y Controller: PARTE 1

		1. Crear nuestro archivo de configuracion maestro llamado "app.js"

		- Este archivo va tener las directivas o el modulo principal de angular de nuestra
			aplicacion

			var app = angular.module('universidadApp', []);

		- Estos argumentos son dependencias que nuestra aplicacion PODRIA utilizar

		2. Añadir el nombre de la aplicación "universidadApp" como valor de la directiva *ng-app

		3. Añadir el controlador *profesorCtrl en el archivo de configuracion maestro

		- CTRL es un estandar entre los desarrolladores de Angular

		- ¿QUE ES UN CONTROLADOR?

			Los controladores son los que se encargan de manejar el totalidad de la pagina
			o una parte de la misma, se recomienta que esten bien encapsulados.

			Por ejemplo:
				- Controlador Profesor (todas las funciones relacionadas con el profesor)
				- Controlador Alumno (todas las funciones relacionadas con los alumnos)
			
		4. Añadir la referencia al archivo javascript en el *Head de la vista 

		5. Añadir la directiva *ng-controller con el valor del controlador creado *profesorCtrl

			<div class="container" ng-controller="profesorCtrl">

		- Todo lo que esta dentro de este bloque lo va manejar el *profesorCtrl

		6. Añadir un alias al controlador

			<div class="container" ng-controller="profesorCtrl as profe">

		7. Utilizar el alias para llenar los espacios con los datos del profesor

		8. Agregar la propiedad *ng-src para que cargue la imagen correctamente

			ng-src="{{ profe.profesor.foto }}"

		ERROR: La imagen no fue encontrada
			- Cuando el navegador empieza a cargar, la libreria de angular aun no esta en 
				el navegador web, por lo que la foto no se encuentra en ningun lado.

			- Cuando termina de ejecutar angular y se inicializa, agrega la imagen.


	DIRECTIVAS App Y Controller: PARTE 2

		1. Agregar una caja de texto para el nombre

		- Solo hay que poner las llaves("{{ }}") cuando ya usamos el "ng-src", caso contrario no porque
			ya es una directiva de Angular 

		2. Agregar una caja de texto para la edad

		3. Agregar una caja de texto para la biografia

		- $scope: 
			Es una variable global, esta fuera del controlador, vive en el ambito de angular.
			Tiene propiedades, funciones, metodos.

		4. En el fichero "app.js" realizar lo siguiente:
			- Pasar al controlador el parametro $scope
			- Asignar a la variable $scope el objeto "profesorData"

		5. Ademas, crear la funcion "EditarProfesor" en el $scope
			- Usar "angular.copy" , primer parametro "lo que copiaremos", segundo parametro "a donde copiar"

		6. Añadir un boton debajo de la "edad" llamado "Editar"
			- Agregar la propiedad "ng-click" y pasarle como valor "EditarProfesor()"

		7. Agregar en la vista los botones "Guardar" y "Cancelar"

		8. Añadir las funcionalidades para los dos botones creados en el punto 7.