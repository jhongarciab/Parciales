# ***Parcial 1***
*Programa de Física, Universidad del Quindío, Marzo, 2023*
*Estudiante:* Jhon Sebastian García Barrera
1. Construya un programa que tenga una clase matriz (puede hacerlo con base en lo realizado en clase) que tenga un método implementado para solucionar un sistema de ecuaciones por el método Gauss-Jordan. La dimensión de la matriz es arbitraria y el programa debe decir si tiene solución única, infinitas soluciones o única solución. La clase debe tener un atributo llamado is valid que es una lista cuyo primer elemento es un Booleando indicando si todos los elementos de la matriz son números o hay algún dato inválido. Si el booleano es True, el segundo elemento de la lista sería una liusta vacía, si es False, el segundo elemento de la lista será una lista con los Indices de los elementos de la matriz que están incorrectos. Ayuda: Si desea hagalo con un N máximo de 5
2. Organice el ejemplo desarrollado en clase (el de matrices) para que los vectores puedan ser ingresados como una sola lista y no como lista de listas.Defina el producto entre matrices, vectores y escalares usando __mul__ y __rmul__ y defina un método para calcular la transpuesta de una matriz y otro uno para determinar si es simétrica.
## ***Bitácora***
El primer día se llevó a cabo el código para matrices cuadradas desde 2x2 hasta 5x5. Un código largo (400 líneas aprox.) pero no difícil, el cual fue una pérdida de tiempo ya que no era útil, pues, el método Gauss-Jordan se puede aplicar no necesariamente a matrices cuadradas y además de eso, solo con un n de 2 hasta 5, por lo que se definió las matrices nxm, con suma y resta de una manera arbitraria usando for anidados. Hasta ahora ha sido lo más demorado, el hecho de entender bien la lógica para desarrollar esa definición desde cero.
Se implementó mul y rmul para llevar a cabo las multiplicaciones entre matrices y escalares, primero fue esto ya que para el método G-J es necesario la multiplicación.