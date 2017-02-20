
Angular 2: Getting Started - SnapShot 4
===================
En esta parte veremos estos contenidos del curso de Pluralshight:

 - More on Components


----------


### 1 - More On Components


----------


En esta sección se hablará de cómo mejorar los componentes mediante técnicas como estas:


![enter image description here](https://i.imgur.com/BhdivyV.png)


.


----------


### 2 - Strong typing & interfaces


----------


Gracias a TypeScript podemos crear interfaces para definir contratos de cualquier tipo. 


![enter image description here](https://i.imgur.com/L8M1m9P.jpg)


 - Una vez definida una interfaz la podemos implementar en una clase.


![enter image description here](https://i.imgur.com/b47MYf1.jpg)


 - Y finalmente la podemos importar en el componente para utilizarla


![enter image description here](https://i.imgur.com/39loDo8.jpg)


.



----------


### 3 - Encapsuling styles


----------


De la misma forma en que podemos tener referenciada la Template HTML con un path también podemos definir Styles de forma inline o referenciando a un fichero CSS:



![enter image description here](https://i.imgur.com/PYWDZFR.jpg)


.



----------


### 4 - Lifecycle hooks


----------


Los Lifecycle hooks son eventos que se producen durante la ejecución de un componente.


Estos eventos pueden ser utilizados para realizar ciertas acciones. Por ejemplo, se puede utilizar el evento **OnInit** para inicializar los datos del componente invocando a un servicio externo.



![enter image description here](https://i.imgur.com/H02CwXS.jpg)


.


**Importante destacar que para cada evento existe una Interface que podemos implementar**. Un ejemplo a continuación


![enter image description here](https://i.imgur.com/Gj5hQNP.jpg)


.


----------


### 5 - Custom pipes


----------


Tal y como ya se ha comentado una Pipe sirve para formatear o transformar un objeto cualquiera. Y hemos visto que existen pipes por defecto para formatear strings, fechas, números, monedas etc.


#### ¿Cómo implementamos y utilizamos una pipe?


#### 1 - Implementando una Interface y exportando nuestra Pipe con un Decorator


![enter image description here](https://i.imgur.com/WcZIChL.jpg)


#### 2 - Registrar la Pipe como módulo y utilizarla en las Templates


![enter image description here](https://i.imgur.com/JmFo7Ly.jpg)


. 



----------


### 6 - Relative paths with ModuleId


----------


Ya hemos visto que los componentes están constituidos por varios ficheros y que en el Decorator se especifican las rutas a dichos ficheros.



![enter image description here](https://i.imgur.com/1Ez9uTE.jpg)



**Inconvenientes de las rutas:** 


 - Si la aplicación empieza a crecer con muchos componentes y estructuras de folders distintas las rutas empiezan a hacerse poco gestionables


 - No es posible reutilizar los componentes con otras aplicaciones


 - Incluso existen ciertas herramientas que requieren de paths relativos.


**¿Solución? **


Hacer uso de la declaración de componentes mediante **module.id**


![enter image description here](https://i.imgur.com/C7kqf7v.jpg)


**¿Qué es Module Id?**


 - Es una variable parcialmente global que está disponible cuando se trabaja con el formato de módulos que provee CommonJS.

 - Contiene la URL absoluta del fichero de módulos

 - Implica que se definan los módulos en el formato de **CommonJS**

 - Implica que se carguen los módulos utilizando **SystemJS** o cualquier otro cargador de modulos compatibe con CommonJS


![enter image description here](https://i.imgur.com/1yuUmFD.jpg)


.


----------


### 7 - Práctica


----------



Para ello clonamos el **SnapShot 4** desde el primer commit:

    git clone https://github.com/tc-frontend/course_angular2_day1_snapshot4
    cd course_angular2_day1_snapshot4
    git checkout tags/init
    npm install
    code .

----------


#### 1 - Crear una interface para los Productos

    export interface IProduct {
        productId: number;
        productName: string;
        productCode: string;
        releaseDate: string;
        price: number;
        description: string;
        starRating: number;
        imageUrl: string;
    }

Cambiar el any[] por IProduct[]

https://goo.gl/Xj16Bf

----------


#### 2 - Añadir un estilo al componente

    thead{
        color: #337AB7
    }

https://goo.gl/zZfEiU

----------
#### 3 -  Implementar OnInit a la clase



https://goo.gl/0CKaei


----------

#### 4 - Construir un pipe (filterBy) personalizado para el filtrado

Este pipe filtrará los productos de la lista por nombre. Así quedaría el pipe


https://goo.gl/aD4VXp

----------

#### 5 - Eliminar los path relativos y utilizar moduleId

https://goo.gl/CsBLLe
 

Los pasos detallados en el historial de commits:

https://goo.gl/K0N0Ab 
  
Si queremos ver la App en nuestro browser

    npm start

Si queremos ver la solución final de este SnapShot:

    git checkout master
    npm install
    npm start
