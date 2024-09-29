# Challenge-04


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

  
<p>Luego damos play y corroboramos que al dar <code>Left click</code> se haga el <code>spawn</code> de las balas correctamente. En el video acontinuación puede ver como se realiza el <code>spawn</code> de las balas.</p>


[![Bullet Spawn](miniatura.png)](Challenge04/bulletSpawn.mp4)




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



  
