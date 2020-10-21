# Tarea No.4 - Investigación

## **Hiperpaginación (Trashing)**

Se produce cuando el procesador consume más tiempo intercambiando fragmentos de memoria (cargando o eliminando páginas o segmentos), que ejecutando las instrucciones realizadas por el usuario.

Esto puede pasar por dos razones:

- Muchas páginas de tamaño grande.
- Muchas páginas pequeñas con nulo o poco uso.

en los dos casos estas páginas llenan la memoria principal y por consiguiente no se utiliza por completo.

### *Posibles causas de la hiperpaginación*

Un proceso necesita más marcos, su taza de fallos de página aumenta y se produce la siguiente reacción en cadena:

- Disminuye el uso de CPU
- El S.O. decide aumentar el grado de multiprogramación
- La tasa de fallos de página se incrementa más

**Soluciones:**

- Reducir la multiprogramación o emplear un algoritmo de reemplazo local o por prioridades
- Prevenir la hiperpaginación

### *Tipos de Hiperpaginación*

***Asignación Fija:*** Es hiperpaginación en proceso P, si conjunto residente de P es menor al conjunto de trabajo P.

***Asignación Variable:*** Es hiperpaginación en el sistema se el número de marcos disponibles es menor a la sumatoria del conjunto de trabajos de los procesos.

En un estado normal esto permite que un proceso bloqueado y no listo para correr deje lugar en memoria principal a otro proceso listo.

Cuando se produce hiperpaginación los ciclos del procesador se utilizan en llevar y traer páginas o segmentos según sea el caso y el rendimiento general del sistema se degrada notablemente, este fenómento puede sufrirlo también el sistema en su conjunto; supongamos un S.O. que controla el grado de utilización del procesador de forma que si es muy bajo aumenta el grado de multiprogramación iniciando más procesos, se utiliza un algoritmo de sustitución de páginas global di un proceso aumenta sus necesidades de memoria provocará faltas de procesos.

## **Principio de Cercanía**

El Principio de Cercanía afirma que las referencias a los datos y al programa dentro de un proceso tienden a agruparse. Por tanto, es válida la suposición de que, durante cortos periodos, se necesitarán sólo unos pocos fragmentos de un proceso. Además, sería posible hacer predicciones inteligentes sobre qué fragmentos de un proceso se necesitarán en un futuro cercano y así evitar la hiperpaginación.

Una manera de confirmar el principio de cercanía es considerar el rendimiento de un proceso en un entorno de memoria virtual. Así pues, se puede comprobar que el principio de cercanía sugiere que los esquemas de memoria virtual pueden funcionar. Para que la memoria virtual sea práctica y efectiva, se necesitan dos ingredientes:

- Debe haber un soporte de hardware
- El sistema operativo debe incluir un software para gestionar el movimiento de páginas y/o segmentos entre memoria secundaria y memoria principal.

## **Soportes de Memoria Virtual**

Es necesario soporte hardware para la traducción de direcciones. Las direcciones lógicas generadas por el programa se dividen en número de página (o segmento) y desplazamiento dentro de la página. La traducción del número de página (o segmento) a marco de página en memoria física (o dirección de comienzo del segmento) se realiza en tiempo de ejecución mediante una tabla de páginas (o tabla de segmentos) asociada al programa, que habitualmente reside en memoria. Además, es conveniente hardware adicional para acelerar la traducción, ya que cada referencia a memoria implica dos accesos a memoria física.
