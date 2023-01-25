## **Tipos de Kernel**

### **Núcleo monolítico (Kernel monolítico):**

En computación, un núcleo monolítico es una arquitectura de sistema operativo donde este en su totalidad trabaja en espacio del núcleo, estando él solo en modo supervisor.

En esta arquitectura hay una correspondencia entre el programa que confirma el sistema operativo y el núcleo en sí.
Este núcleo está programado de forma no modular y puede tener un tamaño considerable. A su vez, cada vez que se añada una nueva funcionalidad, deberá ser recompilado en su totalidad y luego reiniciado. Todos los componentes funcionales del núcleo tienen acceso a todas sus estructuras de datos internas y a sus rutinas. Por ende, un error en una rutina podría propagarse a todo el sistema.

### **Micronúcleo (Microkernel):**

Es un tipo de núcleo de un sistema operativo que provee un conjunto de primitivas o llamadas mínimas al sistema para implementar servicios básicos como espacios de direcciones, comunicación entre procesos y planificación básica. Todos los otros servicios (gestión de memoria, sistema de archivos, operaciones de E/S, etc.), que en general son provistos por el núcleo, se ejecutan como procesos servidores en espacio de usuario.
Las principales ventajas de su utilización son la reducción de la complejidad, la descentralización de los fallos entre otras ventajas. Por otro lado, sus principales dificultades son la complejidad en la sincronización de todos lo módulos que componen el micronúcleo y su acceso a memoria.

### **Núcleo híbrido (Kernel híbrido):**

Básicamente, es un micronúcleo que tienen algo de código <<no esencial>> en espacio de núcleo, para que este se ejecute más rápido de lo que haría si estuviera en espacio de usuario. Este fue un compromiso que muchos desarrolladores de los primeros sistemas operativos, con arquitectura basada en micronúcleo, adoptaron antes de que se mostrará que los micronúcleos pueden tener también muy buen rendimiento.
La mayoría de los sistemas operativos modernos pertenecen a esta categoría, siendo el más popular Microsoft Windows.
El concepto de núcleo híbrido se refiere a que el núcleo en cuestión usa mecanismos o conceptos de arquitectura tanto del diseño monolítico como del micronúcleo, específicamente el paso de mensajes y la migración de código <<no esencial>> hacia el espacio de usuario.

### **Diferencias:**
| Monolítico | Micronúcleo  | Híbrido 

#### ***Monolítico***
- Si se va a agregar un nuevo servicio en el kernel, entonces se debe modificar todo el kernel.
- El diseño requiere menos código, lo que conduce a menos errores.
- Es rápido pero menos seguro.

#### ***Micronúcleo***
- Es fácil extender el microkernel porque se debe agregar un nuevo servicio en el espacio de direcciones de usuario del espacio del kernel.
- Necesita más código, lo que además genera más errores.
- Es más lento, pero más seguro y confiable.

#### ***Híbrido***
- Es la combinación del núcleo monolítico y el micronúcleo.
- El núcleo grande se hace más compacto y modulable.
- Partes del kernel pueden cargarse dinámicamente.

#### Estructura:

![enter image description here](https://www.softwaretestinghelp.com/wp-content/qa/uploads/2019/02/1920px-OS-structure2.svg.png)
[enter image description here](https://www.softwaretestinghelp.com/wp-content/qa/uploads/2019/02/1920px-OS-structure2.svg.png)


## **User vs Kernel Mode**

#### ***User***

- En modo usuario, el programa de aplicación se ejecuta y se inicia.

- En el modo de usuario, un solo proceso falla si ocurre una interrupción.

- El modo de usuario también se conoce como modo sin privilegios, modo restringido o modo esclavo.

- En el modo de usuario, todos los procesos obtienen un espacio de direcciones virtuales separado

- Mientras está en modo usuario, las aplicaciones tienen menos privilegios.

- Solo puede hacer referencias a la memoria asignada para el modo de usuario. 

#### ***Kernel Mode***

- En modo kernel, el programa tiene acceso directo y sin restricciones a los recursos del sistema.

- En el modo Kernel, todo el sistema operativo puede dejar de funcionar si se produce una interrupción.

- El modo kernel también se conoce como modo maestro, modo privilegiado o modo de sistema.

- En modo kernel, todos los procesos comparten un único espacio de direcciones virtuales.

- En el modo kernel, las aplicaciones tienen más privilegios que en el modo usuario.

- Es capaz de hacer referencia a ambas áreas de memoria.


![enter image description here](https://learn.microsoft.com/en-us/windows-hardware/drivers/gettingstarted/images/userandkernelmode01.png)
[enter image description here](https://learn.microsoft.com/en-us/windows-hardware/drivers/gettingstarted/images/userandkernelmode01.png)