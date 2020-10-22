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

El principal objetivo de la planificación a corto plazo es repartir el tiempo del procesador de forma que se optimicen algunos puntos del comportamiento del sistema. Generalmente se fija un conjunto de criterios con los que evaluar las diversas estrategias de planificación. El criterio más empleado establece dos clasificaciones. En primer lugar, se puede hacer una distinción entre los criterios orientados a los usuarios y los orientados al sistema. Los criterios orientados al usuario se refieren al comportamiento del sistema tal y como lo perciben los usuarios o los procesos. Uno de los parámetros es el tiempo de respuesta. El tiempo de respuesta es el periodo de tiempo transcurrido desde que se emite una solicitud hasta que la respuesta aparece en la salida. Sería conveniente disponer de una política de planificación que ofrezca un buen servicio a diversos usuarios.

Otros criterios están orientados al sistema, esto es, se centran en el uso efectivo y eficiente del procesador. Un ejemplo puede ser la productividad, es decir, el ritmo con el que los procesos terminan. La productividad es una medida muy válida del rendimiento de un sistema y que sería deseable maximizar.

Otra forma de clasificación es considerar los criterios relativos al rendimiento del sistema y los que no lo son. Los criterios relativos al rendimiento son cuantitativos y, en general, pueden evaluarse o ser analizados fácilmente. Algunos ejemplos son el tiempo de respuesta y la productividad. Los criterios no relativos al rendimiento son, en cambio cualitativos y no pueden ser evaluados fácilmente. Un ejemplo de estos criterios es la previsibilidad. Sería conveniente que el servicio ofrecido a los usuarios tenga las mismas características en todo momento, independientemente de la existencia de otros trabajos ejecutados por el sistema.

*En particular, una disciplina de planificación debe:*

**Ser equitativa:** debe intentar hacer una planificación justa, esto es, se debe tratar a todos los procesos de la misma forma y no aplazar indefinidamente ningún proceso. La mejor forma de evitarlo es emplear alguna técnica de envejecimiento; es decir, mientras un proceso espera un recurso, su prioridad debe crecer.

**Ser eficiente:** debe maximizar el uso de los recursos tales como intentar que la ocupación de la CPU sea máxima. Al mismo tiempo se debe intentar reducir el gasto extra por considerar que es trabajo no productivo. Normalmente el idear algoritmos eficientes supone invertir recursos en gestión del propio sistema.

**Lograr un tiempo bueno de respuesta**, es decir, que los usuarios interactivos reciban respuesta en tiempos aceptables.

**Lograr un tiempo de proceso global predecible.** Esto quiere decir que un proceso debe ejecutarse aproximadamente en el mismo tiempo y casi al mismo costo con independencia de la carga del sistema.

**Elevar al máximo la productividad o el rendimiento**, esto es, maximizar el número de trabajos procesados por unidad de tiempo. Eso supone, por un lado, dar preferencia a los procesos que ocupan recursos decisivos y, por otro, favorecer a los procesos que muestran un comportamiento deseable. En el primer caso conseguimos liberar el recurso cuanto antes para que esté disponible para un proceso de mayor prioridad. Con el segundo criterio escogemos a los procesos que no consumen muchos recursos dejándole al sistema mayor capacidad de actuación.

**Estos criterios son dependientes entre sí y es imposible optimizar todos de forma simultánea.** Por ejemplo, obtener un buen tiempo de respuesta puede exigir un algoritmo de planificación que alterne entre los procesos con frecuencia, lo que incrementa la sobrecarga del sistema y reduce la productividad. Por tanto, en el diseño de un política de planificación entran en juego compromisos entre requisitos opuestos; el peso relativo que reciben los distintos requisitos dependerá de la naturaleza y empleo del sistema.

## **Prioridades de la planificación**

En este tipo de planificación a cada proceso se le asigna una prioridad siguiendo un criterio determinado, y de acuerdo con esa prioridad será el orden en que se atienda cada proceso.

- El plaanificador seleccionará siempre a un proceso de mayor prioridad antes que a los de menor prioridad.
- Tiene múltiples colas de listos para representar cada nivel de prioridad.
- Los procesos de prioridad más baja pueden sufrir inanición:
  - Permite que un proceso cambie su prioridad en función de su edad o su historial de ejecución.

La prioridad de planificación se calcula a través de la suma de el tiempo de espera más el tiempo de servicio, todo esto entre el tiempo de servicio.

En este algoritmo a cada proceso se le asocia un número entero de prioridad. Mientras menor sea este entero pues mayor prioridad tiene el proceso, por lo que la escencia del algoritmo es planificar la entrada de procesos a la CPU de acuerdo a la prioridad asociada de cada uno de ellos.

Un caso particular del algoritmo por prioridad es el SJF, donde el valor del próximo ciclo de CPU representa la prioridad. El algoritmo por prioridad corrige algunas deficiencias del SJF, particularmente el retraso excesivo de procesos largos y el favoritismo por procesos cortos.

Uno de los problemas que puede presentar esta planificación es la de un bloqueo indefinido. Es decir, pudiera darse el caso que existan procesos de prioridad alta que harán que los procesos de prioridad baja queden bloqueados esperando por ellos, solo se desbloquearán cuando estos procesos de prioridad baja logren colocarse en la CPU y por ello puede darse una espera indefinida.

Es aquí donde se puede aplicar una técnica conocida como envejecimiento que irá incrementando la prioridad de los procesos en espera cada determinado tiempo hasta que estos se ejecuten.

## **Modo de decisión**

Se refieren a como los procesos van a hacer uso del procesador, existen dos modos de decisión

***MODO PREFERENTE:*** el procesador es asignado partiendo de una preferencia es no apropiativa y va depender siempre de un elemento de asignación por parte del procesador.

***MODO NO PREFERENTE:*** es aquel que llegar al uso del procesador se apropia de él y no lo suelta hasta que no haya una interrupción de e/s, el procesador es liberado cuando termina es utilizado mucho en el procesamiento por lotes pese a que una de sus políticas es la más frecuentemente utilizada pero no como una política de planificación de primer nivel.

Para poder establecer las políticas de planificación se tiene que tener en cuenta que se manejan

*Tl:* momento en el cual se admite el proceso

*Ts:* tiempo de servicio tiempo que demora el sistema operativo en ejecutar las operaciones que fueron enviadas por el usuario es decir  tiempo efectivo de utilización del procesador

*Te:* tiempo de espera a diferencia del tiempo de servicio no tiene nada que ver con el programador

*Tr:* tiempo de retorno es el tiempo total de uso del espacio de direcciones  es decir el tiempo de servicio + el tiempo de espera.

*Tw:* tasa de respuesta es un factor que implica el tiempo de servicio y el de espera es decir es el tiempo de Tr/Ts.
