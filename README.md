# Challenge 04: Bullet Time

<h2>Reflexión</h2>
<p>En este reto pudimos dar nuestros primeros pasos a manejar los inputs del jugador para provocar movimientos en un personaje específico. Es interesante lo intuitivo que es el proceso pues simplemente se verifica si las teclas que nos interesa vigilar están siendo presionadas o no. Esto también nos habla de que algo muy importante al programar en un videojuego es tener esa estructuta lógica de saber que ciertos <code>scripts</code> deben estar asociados a un elemento particular del videojuego. Como por ejemplo asociar el código de clonar al prefab de la bala o al manero del input del teclado con el robot.</p>
<p>A pesar de ser bastante intutivo la logica tras este sistema de movimiento de manera scripted, tuvimos la experiencia de traducir el C# script a un Visual Graph, una manera de hecha principalmente para aquellos que no son diestros en lenguajes de programacion. Basado en esta experiencia, podemos concluir que el sistema de Visual Graph, aunque efectivo, es muchisimo mas tedioso y trabajoso manejar ya que se cada cosa se basa en las interacciones de los nodos que ponga el desarrollador y sus conexiones a otros nodos. Esto se debe a que para cada nodo hay que repetidamente buscar en una lista de muchisimos otros nodos y este proceso consume mas tiempo que cuando haces un script directamente para Unity con C#. Es un buen sistema, pero como personas con un poco mas experiencia de lo normal programando, preferimos hacer scripts y no Visual Graphs.</p>


<h2>Instalando <code>Assets</code> que utilizaremos más adelante.</h2>
<p>Comenzamos accesando el Asset Store.</p>
<image
  src="Challenge04/assetStore.png"
  width = 80%
  height = 80%>

<p>Buscamos <code>Robot Hero</code> e instalamos.</p>
<image
  src="Challenge04/robotHero.png"
  width = 80%
  height = 80%>


<p>Dentro de Unity buscamos <code>Package manager</code> asegurandonos que buscamos bajo <code>My Assets</code> escogemos el paquete que queremos importar a nuestro proyecto y presionamos <code>import</code>.</p>
<image
  src="Challenge04/import.png"
  width = 80%
  height = 80%>


<p>Una vez importamos el paquete tenemos que pasarlo por el proceso de <code>rendering</code>.</p>
<image
  src="Challenge04/render.png"
  width = 80%
  height = 80%>


<p>Marcamos <code>Material Upgrade</code> y luego <code>Convert Assets</code>.</p>
<image
  src="Challenge04/rendering.png"
  width = 35%
  height = 35%>


<p>Con este proceso realizado ya podemos instanciar algun prefab de los que el paquete nos incluye.</p>
<image
  src="Challenge04/instanciaRobot.png"
  width = 80%
  height = 80%>




<h2>Creando esfera que fungirá como <storng>bala</storng>.</h2>
<image
  src="Challenge04/bullet.png"
  width = 80%
  height = 80%>


<p>Creamos Folder para los Prefabs y otro para los materiales. Una vez creados estos folders, deslizamos el objeto referente a la bala hacia dentro del folder de Prefabs y borramos la instancia de ese objeto.</p>
<image
  src="Challenge04/prefabFolder.png"
  width = 80%
  height = 80%>


<p>Dentro del Folder para los materiales, creamos un nuevo material. </p>
<image
  src="Challenge04/material.png"
  width = 80%
  height = 80%>


<p> Ajustamos el color del material al deseado.</p>
<image
  src="Challenge04/color.png"
  width = 80%
  height = 80%>


<p>Aplicamos el material al prefab de la bala.</p>
<image
  src="Challenge04/ponerColor.png"
  width = 80%
  height = 80%>


  

<h2>Creamos un nuevo script que esté vinculado con el prefab de la bala.</h2>

<p>Para crear el script seleccionamos el prefab y presionamos <code>Add Component</code> luego seleccionamos <code>New script</code>. Luego seleccionamos <code>Script machine</code> y elegimos el nombre de nuestro script. En este caso le llamamos <code>fowardMovement</code>.</p>
<image
  src="Challenge04/newScript.png"
  width = 80%
  height = 80%>


<p>Creamos un folder para los scripts y movimos el script antes creado hacia el folder llamado <code>scripts</code>.</p>
<image
  src="Challenge04/moveScripts.png"
  width = 80%
  height = 80%>


<p>Antes de escribir código, creamos un objeto vacío dentro de la jerarquía del robot. Este objeto vacío nos servirá como punto referente del lugar de <code>spawn</code> de las balas.</p>
<image
  src="Challenge04/CreateEmpty.png"
  width = 35%
  height = 35%>

<p>Ahora editamos el script llamado <code>fowardMovement</code> que está atado a la bala, entonces lo abrimos presionando 2 veces en el archivo que nos va a aparecer dentro del folder de sripts. Esto abrirá el script en cuestión en el editor que tengamos seleccionado como el de nuestra preferencia, en nuestro caso <Code>Visual Studio Code</Code>. A continuación se muestra una captura del código que debe ir dentro del archivo <code>fowardMovement</code>.</p>
<image
  src="Challenge04/bulletCode.png"
  width = 80%
  height = 80%>


<h2>Creamos un nuevo script que esté vinculado con el asset que importamos.</h2>
<p>Elegimos el nombre de <code>PlayerScript</code>.</p>
<image
  src="Challenge04/AddScriptRobot.png"
  width = 80%
  height = 80%>



<p>En la próxima imagen se añade el código que añadimos al script <code>PlayerScript</code>. El código incluye comentarios descriptivos de lo añadido.</p>
<image
  src="Challenge04/spawnCode.png"
  width = 80%
  height = 80%>


<p>Luego, seleccionamos el robot y en la parte derecha seleccionaremos los <code>Game Objects</code> a los que se hacen referencia en el código.</p>
<image
  src="Challenge04/setReference.png"
  width = 35%
  height = 35%>

  
<p>Luego damos play y corroboramos que al dar <code>Left click</code> se haga el <code>spawn</code> de las balas correctamente. En  <a href="https://youtu.be/610h-I4UDWE?si=PiAp8QNyCGdQ4XSU"> este video</a> puede ver como se realiza el <code>spawn</code> de las balas.</p>




<h2>Adaptación del código en C# a <code>Visual Graph</code>.</h2>

<p>Comenzamos creando un nuevo <code>Visual Scripting</code> vinculado al robot.</p>
<image
  src="Challenge04/AddVisualScript.png"
  width = 80%
  height = 80%>


<p>En la parte izquierda bajo el renglón de <code>Object</code> añadimos las variables que vamos a necesitar.</p>
<image
  src="Challenge04/createObjectVars.png"
  width = 35%
  height = 35%>


<p> "Traducimos" el código en C# al Visual Graph. Cada nodo o "caja" se inserta presionando <code>Right Click >> Add node</code>. Una vez tenemos un pedazo del Visual Graph que realiza una función particular es una buena práctica agrupar todos los nodos. Para mientras presionamos <code>Ctrl</code> seleccionamos los nodos. Luego podemos ponerle un nombre al grupo de nodos, en nuestro caso le llamamos <code>Bullet Spawn</code>.</p>
<image
  src="Challenge04/bulletSpawnGraph.png"
  width = 80%
  height = 80%>

<h2>Creando el terreno y añadiendo el personaje en la escena</h2>

<p>Creamos un terreno sencillo simplemente para probar nuestro personaje. En este caso, utilizamos un material sacado de las librerías que se instalaron anteriormente.</p>

<image src="img/Terrain01.png" width=80% height=80%>
<image src="img/Terrain02.png" width=80% height=80%>
<image src="img/Terrain03.png" width=80% height=80%>

<p>Arrastramos el prefab que creamos del personaje y lo añadimos a la escena de nuestro juego para que esté ubicado en algún punto sobre el terreno.</p>

<image src="img/Character.png" width=80% height=80%>

<h2>Programando movimiento del personaje con teclado</h2>

<p>Volvemos al <code>PlayerScript</code> que ya creamos y lo abrimos en nuestro editor de preferencia. Dentro de la clase, creamos variables para las velocidades de traslación y rotación.</p>

<image src="img/Script02.png" width=80% height=80%>

<p>Dentro de la función <code>Update()</code>, definimos el movimiento del personaje de la siguiente manera:</p>

<image src="img/Script03.png" width=80% height=80%>

<p>Note que todas las velocidades están siendo escaladas por un factor de <code>deltaTime</code>. Esto es para tomar en cuenta la cantidad de FPS a la que corre el juego en cada máquina y que la velocidad sea consistente sin depender de los FPS.</p>

<p>Finalmente, ajustamos la cámara para poder visualizar correctamente el personaje.</p>

<image src="img/Camera.png" width=80% height=80%>

<h3>Una adición de bono</h3>

<p>Para que el "debugging" del juego sea menos tedioso, añadimos las siguientes líneas en la función <code>Start()</code> para que el cursor del ratón no sea visible mientras movemos el personaje.</p>

<image src="img/Bonus.png" width=80% height=80%>
  
<h2>Creando movimiento de personaje en Visual Graph</h2>
<p>Primero, declararemos 2 variables que utilizaremos para el movimiento de nuestro personaje. En la parte del extremo izquierdo podemos definir variables en <code>(New Variable Name)</code> y crearemos
<code>Float speed</code> y <code>Float speedRotation</code>.</p>

<image src="Challenge 4/variables.png" width=50% height=50%>

<h2>Blueprint para movimiento</h2>
<p>Para empezar con nuestro movimiento, queremos crear el blueprint que utilizaremos en todos los movimientos. Para esto, queremos darle <code>Right Click > "Get Key" x2</code> y estos nodos nos van a servir para que el juego reconozca entradas del jugador desde dos llaves distintas. Vayamos al primer nodo y al acercarnos podemos ver que pide un "Key" para reconocer, en este, queremos que reconozca la tecla<code> Key 'W' </code> mientras que en el otro nodo, reconozca la tecla <code> Key 'Up Arrow'</code>, esto es para empezar con nuestro movimiento hacia el frente.</p>

<p>Luego, vamos a pasar estos dos inputs por un operador 'OR' <code>Right Click > Logical Or</code> y los conectaremos via los circulitos violetas en el nodo 'OR' en los sockets A y B. El resultado de este 'OR' debe ser verificado mediante un  nodo 'IF' <code> Right Click > If </code>. Tambien necesitaremos preparar el movimiento del modelo en si, para esto, utilizamos el nodo 'Transform.Translate' <code>Right Click > Translate (X, Y, Z)</code> y conectamos nuestro nodo 'IF' desde la flecha 'True' a la flecha del nodo 'Transform.Translate'. </p>

<p>Finalmente, vamos a querer utilizar nuestra variable 'speed' para poder mover nuestro jugador a la direccion querida. Para comenzar este proceso, necesitamos acceso a la variable: <code> (HOLD) Left Click on 'speed' variable > Drag and Drop in canvas</code>. Ahora debemos tener un nodo 'Get Variable', luego vamos a querer multiplicar esta variable por un 'Delta Time' que se encuentra en <code> Right Click > 'Time' > Get Delta Time</code>. Para realizar la multiplicacion, necesitamos el nodo 'Formula' customizada de la manera: <code>Right Click > Formula</code> y luego, <code>Formula = AB, Inputs = 2</code>, conectar el nodo 'Delta Time' y 'speed' a el nodo 'Formula' y tomar el output (El circulo de la derecha del nodo) y conectarlo al transform en donde corresponda el movimiento, este lo conectaremos a el circulo 'Z'' del nodo 'Translate'</p>

<p>Nuestro blueprint debe verse de esta manera: </p>

<image src="Challenge 4/forward.png" width=50% height=50%>

<h2> Utilizando el Blueprint para las demas direcciones </h2>
<p>Vamos a seleccionar todos los nodos del blueprint con nuestro left click aguantado y vamos a <code>CTRL+C > CTRL+V x2</code> para evitar repetir pasos y solamente usar los nodos que ya creamos.</p>

<h3>Movimiento hacia atras</h3>
<p>Para este movimiento, ya que es en el mismo axis Z y es opuesto al movimiento hacia el frente, queremos cambiar las teclas por las que busca el juego de <code> Key 'W' > Key 'S'</code> y <code>Key 'Up Arrow' > Key 'Down Arrow'</code> y vamos a querer alterar la multiplicacion un poco, como el movimiento es OPUESTO al delantero, pues significa que nos estaremos moviendo en Z de manera NEGATIVA. Para esto, pondremos un nodo nuevo <code>Right Click > Multiply</code> y editaremos nuestro nodo 'Formula' de manera en que: <code> Formula = '-1 A' </code> y <code> Inputs = 1 </code> Ahora desconectamos el nodo 'Delta Time' de 'Formula' y solo dejamos nuestro 'speed' como la variable A del nodo 'Formula'. Ahora, conectamos el resultado de este nodo y Delta Time con las entradas de 'Multiply' de esta manera: </p>

<image src="Challenge 4/orientchange.png" width=50% height=50%>

<p> Finalmente' pondremos el resultado del nodo 'Multiply' al valor de la Z en el nodo 'Transform.Translate' y terminamos nuestra logica para el movimiento hacia atras. Ahora, hagamos una copia de este blueprint para usarse en otro movimiento <code>CTRL+C > CTRL+V</code>.</p>
<image src="Challenge 4/backward.png" width=50% height=50%>

<h3>Movimiento hacia la derecha</h3>
<p>Utilizaremos una copia del primer blueprint ya que el movimiento hacia la derecha es un valor POSITIVO. Para este movimiento, solo vamos a necesitar cambiar las teclas por las que busca el juego: <code>Key 'W' > Key 'D'</code> y <code>Key 'Up Arrow' > Key 'Right Arrow'</code>.  Por ultimo, desconectamos el resultado del nodo 'Formula' de Z y lo conectamos hacia la X del nodo 'Transform.Translate'</p>

<image src="Challenge 4/right.png" width=50% height=50%>

<h3>Movimiento hacia la izquierda</h3>
<p>Para este, usaremos la copia del blueprint de el movimiento hacia atras, cambiaremos las teclas que busca el juego: <code>Key 'S' > Key 'A'</code> y <code>Key'Down Arrow' > Key 'Left Arrow'</code> y cambiamos la conexion del nodo 'Multiply' de la Z hacia la X de el nodo 'Transform.Translate'.</p>

<image src="Challenge 4/left.png" width=50% height=50%>

<h2>Rotacion de Player con Mouse</h2>
<p>Para lograr que nuestro personaje pueda rotar y virarse con la orientacion de nuestro mouse\cursor, necesitamos crear 3 nodos nuevos: <code>Right Click > Get Axis > Axis Name = Mouse X</code>, <code>Right Click > Formula > Formula = A*B and Inputs = 2</code> y <code>Right Click > Transform > Rotate(X, Y, Z)</code>. Conectaremos el resultado del nodo 'Formula' a el 'Y Angle' del nodo 'Transform.Rotation' y para terminar esto, buscaremos nuestra variable 'speedRotation' desde la esquina de la izquierda y le hacemos <code>Drag & Drop</code> al canvas y la conectaremos a el nodo 'Formula'</p>

<image src="Challenge 4/rotation.png" width=50% height=50%>

<p>Como podemos ver en la imagen, tenemos un nodo extra que nos va a ser sumamente importante para el final de esta grafica, el nodo 'Sequence'. Para ponerlo, haremos <code>Right Click > Sequence > Steps = 6</code>, la razon por la que usamos 6 steps es porque con este nodo es que conectaremos TODOS los nodos 'IF' al nodo principal 'Update' para que corran simultaneamente. Simplemente, conectemos uno de las muchas flechitas saliendo del nodo 'Sequence' a un nodo 'IF' de cada uno de los movimientos como este ejemplo y conectemos el nodo 'Update' al nodo 'Sequence' y ahora todo correra simultaneamente.</p>

<image src="Challenge 4/sequence.png" width=50% height=50%>

<h2> BONO: Cursor Invisible y Locked </h2>
<p>Como decidimos utilizar la funcionalidad de esconder y lock el cursor para que no moleste en debugging, lo decidimos hacer en visual graphing tambien. Primero, se crea un nodo <code>Right Click > 'Sequence' > Steps = 2</code>, y luego dos nodos <code>Right Click > Cursor > Set Visible</code>, <code> Right Click > Cursor > Set Lock State > Locked</code> y conectamos los nodos del cursor a los pasos de 'Sequence' y este lo conectamos al nodo 'On Start' para que tome efectividad en el primer frame. </p>

<image src="Challenge 4/cursor.png" width=50% height=50%>

<h2>Finale de Visual Graph</h2>

<image src="Challenge 4/final.png" width=50% height=50%>
