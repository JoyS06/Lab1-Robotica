# Lab1-Robotica
Lab 1 Robotica

# Descripción de la solución planteada

Para abordar esta tarea, se debe iniciar un nuevo proyecto seleccionando un robot modelo IRB140_6_81, el mismo modelo que se dispone en el laboratorio. Se optó por utilizar un controlador virtual versión 6.15.03 Build 3019. Luego, se debe configurar un objeto de trabajo, situándolo entre el tercer y cuarto cuadrante en relación con el sistema de coordenadas.

![Sup incl](https://github.com/JoyS06/Lab1-Robotica/assets/105253521/285edf05-294e-4022-b519-ac2c7c40bb90)

Para realizar las trayectorias primero se realizó en inventor el modelo de las letras a escribir.

![image](https://github.com/JoyS06/Lab1-Robotica/assets/105253521/fd917d84-107b-4361-9335-05485ae88c02)

El modelo se integró en RobotStudio, donde se estableció el sistema de coordenadas alineado con la orientación de la herramienta. A continuación, se procedió a marcar los puntos a lo largo del contorno de las letras y los puntos más altos para facilitar el cambio entre letras. Una vez hecho esto, se generaron las trayectorias a una velocidad predeterminada de 100. Inicialmente, se emplearon comandos de movimiento lineal (moveL) y todo funcionó sin problemas. No obstante, para adaptarse a la ejecución fue necesario ajustar algunas trayectorias utilizando comandos de movimiento conjunto (moveJ). Es importante destacar que la secuencia programada también incorporó la transición desde la posición inicial o "home" del robot hacia el comienzo de las letras.

![image](https://github.com/JoyS06/Lab1-Robotica/assets/105253521/b875b740-5861-4701-bc05-c73c81540c43)

![image](https://github.com/JoyS06/Lab1-Robotica/assets/105253521/a6d305d9-b77e-4215-ac39-7baf79a46717)

# Diagrama de flujo de las acciones del robot

![Diagrama flujo robotica](https://github.com/JoyS06/Lab1-Robotica/assets/66972115/b9d702f2-e575-4852-b66c-6cde12a1057f)

# Descripción de las funciones utilizadas

![image](https://github.com/JoyS06/Lab1-Robotica/assets/105253521/44e84a7a-a645-4355-906d-024002a53a24)

La función Path10() está diseñada para trazar el contorno del logo, estableciendo las directrices operativas para el robot. Inicia con el comando "MovelJ", que instruye al robot a desplazarse hacia una ubicación determinada. Para asegurar una ejecución precisa, se fijan las velocidades de movimiento: se establece una velocidad general de 100, aplicable tanto al movimiento global como al desplazamiento específico en el eje z, identificados como v100 y z0. Finalmente, se define la herramienta específica a utilizar y se delimita el área de trabajo en la que el robot ejecutará las tareas. 

![image](https://github.com/JoyS06/Lab1-Robotica/assets/105253521/4430a83d-bb30-4632-8974-d5d03d372b9c)

Este código es parte de un procedimiento de RAPID, el lenguaje de programación utilizado en robots ABB, que controla la secuencia de operaciones basadas en la activación de señales digitales de entrada (DI) y la manipulación de señales digitales de salida (DO). Su propósito es ejecutar diferentes trayectorias predefinidas (Path_10, Path_20, Path_30) cuando se reciben señales de entrada específicas.

En un ciclo continuo (WHILE TRUE), se espera una señal de entrada (WaitDI), tras lo cual se activa una señal de salida correspondiente (SetDO). La señal de entrada indica una solicitud para comenzar una operación, como podría ser el inicio de un movimiento de robot o una rutina de trabajo. Una vez que la señal de entrada se desactiva y se activa nuevamente, se ejecuta una trayectoria predeterminada (Path_10). Luego, el proceso se repite para otras señales y trayectorias.

Este ciclo se mantiene indefinidamente, permitiendo al robot responder continuamente a las señales de entrada para llevar a cabo acciones de acuerdo con los requerimientos del laboratorio, que incluyen la comprensión y la manipulación de señales digitales para controlar las operaciones de un robot industrial.

![image](https://github.com/JoyS06/Lab1-Robotica/assets/105253521/33f201aa-f1bf-495a-a4f9-24624bbae36b)

El PROC Path_20() define un procedimiento que usa el comando MoveJ para mover el robot a la posición "Mantenimiento" con una velocidad de 100 mm/s y sin zona de deceleración (z0), lo que significa que el movimiento debería terminar exactamente en el punto de destino sin una zona de aproximación

El PROC Path_30() es similar pero lleva al robot de vuelta a la posición "home". 

# Conclusiones

El laboratorio permitió experimentar con la calibración de herramientas y la definición de sistemas de coordenadas, lo cual es vital para la precisión en las operaciones de robótica. Las actividades prácticas implicaron la programación de trayectorias para realizar tareas de marcado en superficies planas, lo que requería una comprensión clara de las instrucciones de movimiento como MoveL y MoveJ, y cómo estas se aplican en un espacio de trabajo tridimensional.

Se aplico teoría y práctica en el manejo de señales de entrada y salida digitales para controlar secuencias de operaciones, un aspecto fundamental de la automatización en robótica industrial. La importancia de las señales digitales quedó demostrada en la capacidad de iniciar y detener rutinas de movimiento y en la integración de estas señales dentro del flujo de trabajo del robot.

Además, la adaptabilidad del robot a diferentes escenarios de trabajo fue explorada, como se evidencia en la transición de movimientos en superficies planas a planos inclinados. Esta adaptabilidad es crucial en entornos industriales donde los robots deben ser capaces de manejar una variedad de tareas bajo diferentes condiciones operativas.

# Dibujo inclinado con robot ABB 

Dibujo con el robot fisico: https://www.youtube.com/watch?v=mab4iMSGkUU

Entradas y salidas digitales: https://youtu.be/8X4bTrhIlWE?feature=shared

Simulacion: https://www.youtube.com/watch?v=ifNBjNAZaoc

# Dibujo horizontal con robot ABB

Dibujo con el robot fisico con entradas y salidas digitales https://youtu.be/JHbbnv5C7v0?feature=shared

Simulacion: https://www.youtube.com/watch?v=wB2ium5T5FU


