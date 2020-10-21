# Investigación No.6

## **Políticas de Lectura:**

- Está relacionada con la decisión de cuando se debe cargar una página en la memoria principal.
- Con la paginación por demanda, se trae una página a la memoria principal sólo cuando se hace referencia a una posición en dicha página.
  - Cuando un proceso se ejecute por primera vez, se producirán muchos fallos de página.
- Con la paginación previa, se cargaran más páginas de las necesarias:
  - Es más eficiente traer a la memoria un número de páginas contiguas.

## **Políticas de Reemplazo:**

- *Política de ubicación:*
  - Qué página se va a reemplazar.
  - La página que se va a reemplazar tiene que ser la que tenga una menor posibilidad de ser referida en un futuro cercano.
  - La mayoría de las políticas intentan predecir el comportamiento futuro en función del comportamiento pasado.
- *Bloqueo de marcos:*
  - Cuando un marco está bloqueado, la página cargada en ese marco no puede ser reemplazada.
  - La mayoría del núcleo del sistema operativo está en marcos bloqueados.
  - Estructuras de control.
  - Buffers de E/S.
  - El bloqueo se consigue asociando un bit de bloqueo a cada marco.

### **Algoritmos básicos de reemplazo:**

- *Política óptima:*
  - Selecciona para reemplazar la página que tiene que esperar una de mayor cantidad de tiempo hasta que se produzca la referencia siguiente.
  - Es imposible de implementar porque requiere que el sistema operativo tenga un conocimiento exacto de los sucesos futuros.
- *Política de la usada menos recientemente (LRU):*
  - Reemplaza la página de memoria que no ha sido referenciada desde hace más tiempo.
  - Debido al principio de cercanía, ésta sería la página con menor probabilidad de ser referenciada en un futuro cercano.
  - Una solución sería etiquetar cada página con el momento de su última referencia.
- *Política de primera en entrar primera en salir (FIFO):*
  - Trata a los marcos asignados a un proceso como un buffer circular.
  - Las páginas se suprimen de la memoria según la técnica de un turno rotatorio (*round-robin*).
  - Es una de las políticas de reemplazo más sencillas de implementar.
  - Se reemplaza la página que ha estado más tiempo en la memoria.
  - Estas páginas pueden necesitarse de nuevo y en un plazo de tiempo corto.
- *Política del reloj:*
  - Requiere asociar un bit adicional a cada marco, denominado bit de uso.
  - Cuando se carga una página por primera vez en un marco de memoria, el bit de uso de dicho marco se pone a cero.
  - Cuando se hace referencia a la página posteriormente, el bit de uso se pone a 1.
  - Cuando llega el momento de reemplazar una página, el primer marco encontrado con el bit de uso a 0 es reemplazado.
  - Durante la búsqueda para realizar reemplazos cada bit a 1 se cambia a 0.
- *Almacenamiento intermedio de páginas:*
  - La pista de la página reemplazada se asigna a una de las dos listas siguientes:
    - La lista de páginas libres, si la página no ha sido modificada.
    - La lista de páginas modificadas, si lo ha sido.
