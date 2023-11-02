## Laboratorio No. 2 - Robótica Industrial
### Integrantes: 
- Victor Manuel Dávila Castañeda.
- Manuel Felipe Carranza Montenegro.
## Descripción de la solución planteada
El propósito de este laboratorio es controlar el comportamiento de un robot mediante un panel de control. Al presionar el primer botón, se activará una rutina de escritura, mientras que el segundo botón pondrá en marcha una rutina que posicionará el robot en una ubicación conveniente para la colocación de la herramienta de trabajo. Asimismo, se asignarán indicadores que se activarán mientras se esté ejecutando la rutina correspondiente.

## Configuración Entradas y Salidas Digitales (I/O)
Para gestionar las señales, se pueden crear las señales correspondientes en el controlador. Esto se logra haciendo clic derecho en la lista de señales preexistentes y especificando el tipo de señal, siendo 'Entrada Digital' para los botones y 'Salida Digital' para los indicadores.

<div>
<p style = 'text-align:center;' align="center">
<img width="1438" alt="Signals" src="https://github.com/victordavila2311/LAB2Robotica_Manuel_Victor/assets/82252851/1d066fb5-5726-41c5-b600-9106afdf37f1"> 
</p>
</div>

Una vez se han creado las seãles (DI_01, DI_02, DO_01 y DO_03), las cuales serán las encargadas de determinar la lógica de funcionamiento de las rutinas a ejecutar, se tiene que cada una de ellas cumple con la función que se detalla a continuación:

<div>
<p style = 'text-align:center;' align="center">
<img width="773" alt="I:O" src="https://github.com/victordavila2311/LAB2Robotica_Manuel_Victor/assets/82252851/0f0a2e82-9e3a-4125-b623-6adc0e04dc4d"> 
</p>
</div>


## Código de Estructuras de Control
A continuación, procederemos al programa RAPID para establecer la lógica de activación de una rutina determinada, la cual se ejecutará cuando la señal de entrada esté activa.

<div>
<p style = 'text-align:center;' align="center">
<img width="899" alt="Rutine" src="https://github.com/victordavila2311/LAB2Robotica_Manuel_Victor/assets/82252851/f048faf4-b7fa-4c25-b4da-595917e62066">
</p>
</div>

### Reset DO_01; y Reset DO_03;: 
Estos comandos reinician las salidas digitales DO_01 y DO_03 del robot, asegurándose de que estén en su estado inactivo al comienzo del programa.

### WHILE TRUE DO: 
Esto inicia un bucle infinito que se ejecutará continuamente mientras la condición TRUE (verdadera) sea cierta, lo que significa que el bucle no tiene un punto de parada natural y se ejecutará indefinidamente.

### IF DI_01 = 1 THEN: 
En esta parte del código, se verifica si la señal de entrada digital DI_01 está activada (con un valor igual a 1). Si la condición es verdadera, se ejecuta el siguiente bloque de instrucciones hasta que encuentre ENDIF.

### Set DO_01;: 
Esto activa la salida digital DO_01, lo que implica la ejecución de la rutina de escitura de los nombres por parte del robot (V, I, C, T, O, R, M, A, N, U, E, L, RAYO).

### HOME; y Reset DO_01;: 
Estos comandos muestran "HOME" en la pantalla y luego desactivan la salida digital DO_01. El propósito es el retorno del robot a la posición de "HOME" y una vez suceda esto se apagará la salida DO_01 con la finalidad de esperar instrucciones del operador.

### ENDIF: 
Esto marca el final de la primera condición IF.

### IF DI_02 = 1 THEN: 
Similar al primer bloque, este bloque verifica si la señal de entrada digital DI_02 está activada. Si es así, se ejecuta el siguiente bloque de instrucciones.

### Set DO_03;: 
Este comando activa la salida digital DO_03, la cual tiene como finalidad activar la rutina de mantenimiento o el posicionamiento del robot para el cambio de herramienta (TC).

### Reset DO_03;: 
Este comando es el encargado de mantener el robot en la posición de Mantenimiento y esto se apagará la salida DO_03 con la finalidad de esperar instrucciones del operador.

### ENDIF: 
Marca el final de la segunda condición IF.


## Video, simulación e implementación (hacer click en las imagenes)
1) Simulación
<div>
<p style = 'text-align:center;' align="center">
<a href="https://youtu.be/eCq7w-T6ZTA"><img src="https://github.com/victordavila2311/LAB1Robotica_Manuel_Victor/blob/main/imagenes_simulacion/imagen%20simulacion%20horizontal.png" 
alt="IMAGE ALT TEXT HERE" width="380" height="319.5" border="10" /> </a> 
</p>
</div>

2) Implementación
<div>
<p style = 'text-align:center;' align="center">
<a href="https://youtu.be/JX_vcEQwUKw" target="_blank"><img src="https://github.com/victordavila2311/LAB2Robotica_Manuel_Victor/blob/main/imagenes%20lab%202/imagen%20implementacion.png" 
alt="IMAGE ALT TEXT HERE" width="380" height="319.5" border="10" /> </a> 
</p>
</div>

3) Resultado Implementación
<div>
<p style = 'text-align:center;' align="center">
<img src="https://github.com/victordavila2311/LAB2Robotica_Manuel_Victor/blob/main/imagenes%20lab%202/resultado%20implementacion.jpeg" width="300px">
</p>
</div>

