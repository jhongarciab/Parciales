<h1 align="center">Parcial 1 😥</h1> 

#### Estudiante: *Jhon Sebastian García Barrera*

#### Programa de Física, Universidad del Quindío, Marzo, 2023.

1. Construya un programa que tenga una clase matriz (puede hacerlo con base en lo realizado en clase) que tenga un método implementado para solucionar un sistema de ecuaciones por el método Gauss-Jordan. La dimensión de la matriz es arbitraria y el programa debe decir si tiene solución única, infinitas soluciones o única solución. La clase debe tener un atributo llamado is valid que es una lista cuyo primer elemento es un Booleando indicando si todos los elementos de la matriz son números o hay algún dato inválido. Si el booleano es True, el segundo elemento de la lista sería una liusta vacía, si es False, el segundo elemento de la lista será una lista con los Indices de los elementos de la matriz que están incorrectos. Ayuda: Si desea hagalo con un N máximo de 5
2. Organice el ejemplo desarrollado en clase (el de matrices) para que los vectores puedan ser ingresados como una sola lista y no como lista de listas.Defina el producto entre matrices, vectores y escalares usando __mul__ y __rmul__ y defina un método para calcular la transpuesta de una matriz y otro uno para determinar si es simétrica.

<h1 align="center">Bitácora</h1>

El primer día se llevó a cabo el código para matrices cuadradas desde 2x2 hasta 5x5. Un código largo (400 líneas aprox.) pero no difícil, el cual fue una pérdida de tiempo ya que no era útil, pues, el método Gauss-Jordan se puede aplicar no necesariamente a matrices cuadradas y además de eso, solo con un n de 2 hasta 5, por lo que se definió las matrices nxm, con suma y resta de una manera arbitraria usando for anidados. Hasta ahora ha sido lo más demorado, el hecho de entender bien la lógica para desarrollar esa definición desde cero.
Se implementó mul y rmul para llevar a cabo las multiplicaciones entre matrices y escalares, primero fue esto ya que para el método G-J es necesario la multiplicación.

Por ahora la proyección es primero definir un método para intercambiar filas, luego hacer gauss por aparte y luego hacer el jordan. Lo que se lleva hasta ahora no ha sido probado en ejemplos, voy suponiendo que el código funciona de buena manera así, después nos ocupamos de los errores que vayan saliendo. Hecho el intercambio de filas, al empezar con Gauss fue necesario primero añadir un método para encontrar el pivote, pues es necesario para seguir. Hecho Gauss, voy a proceder a hacer pruebas tanto de imprensión, suma, resta, multiplicación, intercambio de líneas y luego Gauss, para no tener problemas en un futuro con errores en conjunto.

El primer error sale a la luz, al momento de sumar y restar, la suma funcionó de manera correcta pero la resta no funcionó. El problema no se debía directamente al código, pasaba que si se imprimía una primero que la otra, esa última no servía, aún no se soluciona esto. Al final el problema sí estuvo en el código, lo que hice fue modificar tanto el código de add como el de sub, añadiendo una nueva lista donde se agregarían los valores calculados de la nueva matriz y ya funcionó. Ahora las pruebas de la multiplicación, el intercambio de filas y Gauss. El primer encuentro para tener en cuenta allí es que la multiplicación solo se definió entre matrices, no por escalar, por lo que se agregará eso, añadiendo un nuevo método para solo la multiplicación por escalar, ya que el primer condicional de la multiplicación es que sean iguales, un escalar es distinto a la matriz por lo que lo voy a tratar en otro método. Sigue habiendo un error ya que (*) se usa para multiplicar entre matrices y la matriz tiene un condicional para verificar que sean ambas matrices con el tamaño apropiado, por lo que al ingresar un escalar lo ve como error, para eso se usará (.escalar) y así hasta ahora funciona correctamente mul, rmul y escalar. El método de Gauss también funciona correctamente hasta ahora.

Una vez definido el método Gauss y Jordan, llegué a la conclusión de que hacerlos de manera separada era contraproducente ya que al momento de pedirlo en la consola tocaría hacerlos por separado y no unificado, por lo que los voy a unir ambos en una sola definición. También no fue difícil hacer este método ya que el Jordan era solo invertir el orden del recorrido de las filas y ahí aplicar las operaciones correspondientes a cada una.

Ahora se implementará un método para decidir si el sistema tiene única solución, infinitas o no tiene. Esto lo hice usando los pivotes, primero se calcula el número de variables en el sistema, que sería igual al número de columnas menos una, la de los términos independientes. Luego, se itera a través de las filas de la matriz. Si una fila tiene todos los elementos iguales a cero, se considera una fila de ceros. Si una fila no es una fila de ceros, se busca el primer elemento no nulo en la fila. El índice de la columna de este elemento no nulo se agrega a la lista de pivotes. Después de iterar a través de todas las filas, se verifica el número de pivotes que se han encontrado. Si hay un pivote para cada variable, el sistema tiene una solución única. Si hay menos pivotes que variables, el sistema tiene infinitas soluciones. Si no hay suficientes pivotes para todas las variables y algunos términos independientes no son cero, entonces el sistema no tiene solución.

Al hacer pruebas de la funcionalidad del código "Tipo de solución" se tiene el problema de que la definición de gauss-jordan solo emite una matriz, no da el vector resultado, por lo que se va a implementar un método de vector resultado. Después de implementar el resultado, se hicieron pruebas para ver la impresión del mismo y que no hayan códigos en el mismo. Todo bien por ahora.

La siguiente parte del parcial se trata de ingresar un atributo llamado Is Valid, el cual recorre la matriz y verifica si cada elemento es un número (int o float), en caso contrario agrega su índice a una lista de índices inválidos. Si la lista está vacía, entonces todos los elementos son números y el atributo is_valid es una lista verdadera, indicando que la matriz es válida. Si la lista no está vacía, entonces la matriz contiene elementos inválidos y el atributo is_valid es una lista [False, indices_invalidos], donde indices_invalidos es la lista con los índices de los elementos inválidos. Y se añadió al principió del código, no sé si sea necesario sólo añadirlo una vez, ya que al ser la encargada de correir y verificar los elementos, podría ser necesario ultilizarlo en cada definición, pero, se dejará solo en el inicio del código esperando a errores futuros.

Después de terminar el punto 1 del parcial, puedo afirmar que la parte más díficil fue definir el método matriz con su respectiva suma, multiplicación, etc. Claramente lo otro no fue sencillo, pero el hecho del estudio necesario para entender a profundidad el ciclo for al momento de definir la matriz fue base suficiente para no tener problemas en el resto de definiciones del código hasta ahora.

En el segundo punto, lo primero es organizar las matrices para que su ingreso sea como una lista y no como lista de listas, para esto voy a crear otra definición donde haya una lista vacía y usando el ciclo for agregar cada sublista a la lista. No sé si esto sea lo más optimo para el ejemplo que se está desarrollando pero es lo que se me viene a la cabeza por ahora, si no ese apropiado, en el futuro se cambiará al momento de errores. Crear una nueva definición no sirvió, por lo que voy a re-definir el __init__ de la clase matriz para que ahora sea una lista plana con los valores de la matriz, por lo que toma tres parámetros (valores, n, m). Al hacer la prueba sí funciona la definición nueva en la que "self.valores" es una lista que contiene los valores de la matriz, donde "self.valores[i][j]" representa el valor en la fila i y la columna j de la matriz.