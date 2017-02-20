Angular 2: Getting Started - SnapShot 6
===================
En esta parte veremos estos contenidos del curso de Pluralshight:

 - Services & dependency injector
 - Retrieving data uning Http

Services & dependency injector
-------------------
![enter image description here](https://i.imgur.com/oEwLVGg.png)

Las aplicaciones necesitan servicios por ejemplo para la obtencion de datos o para implementar un sistema de logging

Tenenmos dos manaeras de instanciar un objeto utilizando new() o dejando esta responsabilidad a Angular. En el primer caso la instacia quedaria asociada al componente y ningun otro comonentete la prodria utilizar. Tambien es mas dicifil crear servicios Mock para testing. En definitiva, es muy aconsejable utilizar la injeccion de dependencias que nos da Angular.

#### Building a service
Cualquier clase que este decorada con @Injectable() tiene la capacidad de poder ser utilizadda en cualquier componente
En nuestro caso vamos a construir un servicio que nos devuelva los productos. De esta manera quitaremos esa logica de negocio del componente y lo podremos utilizar en otros futuramente.
#### Registring the service
Registraremos nuestro servicio con la propiedad **providers** al cual le asignaremos un array con los servicios que utiiará. Este servicio estara disponible en el componente y todos sus hijos.
Para tener disponible el servicio en toda la Aplicacion definimos el componente en el App.module

#### Injecting the service
Para injectar un servico simplemte lo que tenemos que hacer es requerirlo mediante el constructor

Retrieving data uning Http
-------------------
#### Obsevables and Reactive Extenxions
Nos ayudan a manejar la obtencion de datos asincronos 
Estan dentro de la propuesta del nuevo ES 2016
Para utilizarlos necesitamos la libreria de terceros: RxJS la qcual es usada dentro de Angular.
A pesar de esto podemos  volver al modelo clasico de promises aunque tiene unas cuantas diferencias a consierar:
![enter image description here](https://i.imgur.com/jqlhFea.png)
#### Sending and HTTP Request and exception handling
Debemos injectar el servicio Http e importar el HttpModule dentro de la definición del modulo
Utilizaremos el metodo get para obtener un **Observable < Response>**. Transformamos ese objeto en un array obsevable **Observable<IProduct[]>** medante el metodo  map de RxJS
Para manejar las excepciones utilizaremos los metodos do y catch de RxJS
#### Subscribing to an Observable
  Todo objet observable tiene una metodo **subscribe** el cual nos notificará cuandolos datos esten disponible o se haya producido una excepción. 
  
Para ello clonamos el **SnapShot 6** desde le primer commit de:

    git clone https://github.com/tc-frontend/course_angular2_day1_snapshot6
    git checkout HEAD~1
    npm install
    code .
 
Seguimos los pasos detallados en el historial de commits:

    https://github.com/tc-frontend/tc-frontend-angular2_day1_snapshot6/commits/master   
  
Si queremos ver la App en nuestro browser

    npm start

Si queremos ver la solucion final de este SnapShot:

    git checkout master
    npm install
    npm start

