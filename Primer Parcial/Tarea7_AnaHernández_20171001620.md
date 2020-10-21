# <span style="color:blue">Investigación No.7</span>

## **Tamaño Del Conjunto Resistente**

- ***Asignación Fija:***
  - Otorga a cada proceso un número fijo de páginas en las que ejecutar.
  - Cada vez que se produce un fallo de página en la ejecución de un proceso, se debe reemplazar una de las páginas de dicho proceso.

- ***Asignación variable:***
  - Permite que el número de marcos asignados a un proceso cambie a lo largo de su vida.

## **Políticas De Vaciado**

- ***Vaciado por demanda:***
  - Una página se escribirá en la memoria secundaria sólo cuando haya sido elegida para reemplzarse.

- ***Vaciado previo:***
  - Escribe las páginas modificadas por lotes.

La mejor solución es incorporar almacenamiento intermedio de páginas:

- Las páginas reemplazadas pueden situarse en dos listas.
  - *Modificadas*
  - *No modificadas*

- Las páginas de la lista modificadas pueden escribirse periodicamente por lotes.
- Una página de la lista de no modificadas pueden reclamarse, si se le hace de nuevo referencia o perderse, cuando se asigna su marco a otra página.

## **Control De Carga**

- Determina el número de procesos que pueden estar en la memoria principal.
- Cuando hay pocos procesos residentes en la memoría, habrá muchas ocasiones en las que todos los procesos estén bloqueados y se gastará mucho tiempo en el intercambio.
- Si hay demasiados procesos residentes, el resultado será la hiperpaginación.

## **Suspensión de Procesos**

- Procesos con la prioridad más baja.
- Procesos con fallos de página:
  - Este proceso no tiene su conjunto de trabajo en la memoria principal, por lo que quedará bloqueado de todas formas.

- Último proceso activado:
  - Este es el proceso con menos posibilidades de tener su conjunto de trabajo residente.

- Proceso con el conjunto residente más pequeño:
  - Este es el proceso que necesita el menor esfuerzo futuro para volver a cargar el conjunto residente.

- El proceso mayor:
  - Esta alternativa obtiene la mayor cantidad de marcos libres.

- Procesos con la mayor ventana de ejecución restante.
