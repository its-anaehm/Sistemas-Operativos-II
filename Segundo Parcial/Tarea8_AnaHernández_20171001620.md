# <span style="color:blue">**Investigación No.8**</span>

## **Tipos de Planificación**

Los tipos de planificación son:

- Planificación a largo plazo
- Planificación a medio plazo
- Planificación a corto plazo
- Planificación de E/S

***Planificación a Largo Plazo:***

Este planificador está presente en algunos sistemas que admiten además de procesos interactivos trabajos por lotes. Usualmente, se les asigna una prioridad baja a los trabajos por lotes, utilizándose estos para mantener ocupados a los recursos del sistema durante períodos de baja actividad de los procesos interactivos. 

- Determina cuáles son los programas admitidos en el sistema.
- Controla el grado de multiprogramación.
- Cuantos más procesos se crean, menor es el porcentaje de tiempo en el que cada proceso se puede ejecutar.

***Planificación a Medio Plazo:***

En los sistemas de multiprogramación y tiempo compartido varios procesos residen en la memoria principal. El tamaño limitado de ésta hace que el número de procesos que residen en ella sea finito. Puede ocurrir que todos los procesos en memoria estén bloqueados, desperdiciándose así la CPU.

- Forma parte de la función de intercambio.
- Se basa en la necesidad de controlar el grado de multiprogramación.
- En un sistema que no emplee memoria virtual, la gestión de memoria también es un punto a tratar.

***Planificación a corto plazo:***

La planificación de la CPU, en el sentido de conmutarla entre los distintos procesos, es una de las funciones del sistema operativo. Este despacho es llevado a cabo por un pequeño programa llamado planificador a corto plazo .

- También conocido como distribuidor.
- Es el de ejecución más fuerte.
- Se ejecuta cuando ocurre un suceso:
  - Interrupciones del reloj.
  - Interrupciones de E/S.
  - Llamadas al sistema operativo.
  - Señales.

***Planificación de E/S:***

Planificación de E/S (entrada/salida) es el término utilizado para describir el método mediante el cual los sistemas operativos deciden el orden por el cual se van a enviar las peticiones de lectura y escritura al subsistema de disco. A veces se le llama también planificación de disco.

Existen varias razones por las que puede ser deseable aplicar métodos de planificación de E/S:

- Minimizar el tiempo de búsqueda (seek time) en el disco.
- Dar prioridad a las peticiones de E/S de ciertos procesos.
- Dar una porción del ancho de banda de lectura del disco a cada proceso.
- Garantizar que ciertas peticiones se atenderán antes de un tiempo determinado: la conocida como deadline (línea de la muerte en inglés).

![Simbología D-ER](https://drive.google.com/uc?export=view&id=1FkQdCo4RUwjei9x_4jV36o0apym7Iwmm "Simbología D-ER")

## **Criterios de la planificación a corto plazo**

- Orientados al usuario:
  - Tiempo de respuesta:
    - Periodo de tiempo transcurrido desde que se emite una solicitud hasra que la respuesta aparece en la salida.

- Orientados al sistema:
  - Uso efectivo y eficiente del procesador.

- Relativos al rendimiento del sistema:
  - Cuantitativos.
  - Pueden evaluarse fácilmente. Algunos ejemplos son el tiempo de respuesta y la productividad.

- No relativos al rendimiento del sistema:
  - Cualitativos.
  - Previsibilidad.

## **Prioridades de la planificación**

- El plaanificador seleccionará siempre a un proceso de mayor prioridad antes que a los de menor prioridad.
- Tiene múltiples colas de listos para representar cada nivel de prioridad.
- Los procesos de prioridad más baja pueden sufrir inanición:
  - Permite que un proceso cambie su prioridad en función de su edad o su historial de ejecución.

## **Modo de decisión**

- No preferente:
  - Una vez que el proceso pasa al estado de ejecución, continúa ejecutando hasta que termina o se bloquea en espera de una E/S.
  
- Preferente:
  - El proceso que está ejecutando actualmente puede ser interrumpido y pasado al estado de listos por el sistema operativo.