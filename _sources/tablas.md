# Tablas

Las tablas son uno de los elementos más complejos de $\LaTeX$, ya que, aunque es fácil crear una tabla sencilla, aplicarles un formato más avanzado con justificación de columnas, fusión de columnas o filas, márgenes de columnas, líneas de división, etc. suele ser bastante más difícil, aunque algunos entornos de edición facilitan la tarea.  Existen multitud de paquetes para personalizar las tablas pero en esta sección solo veremos lo más básico.

Para crear una tabla se utiliza el entorno `tabular`. Este entorno tiene como argumento obligatorio el número de columnas de la tabla y su justificación, que se indica con una letra: `l` izquierda, `r` derecha y `c` centrada, (por ejemplo `lcr` indica tres columnas, la primera justificada a la izquierda, la segunda centrada y la tercera justificada a la derecha).

A continuación se introduce el contenido de la tabla, separando las filas con el comando de cambio de línea `\\` y dentro de cada línea separando las celdas con el comando `&`. 

**Ejemplo**

```latex
% CUERPO
\begin{document}
% Tabla con tres columnas, justificadas a la izquierda, centrada y derecha.
\begin{tabular}{lcr}
Nombre & Ciudad & Edad \\
María & Valencia & 22 \\
Juan & Madrid & 50 \\
Carmen & Barcelona & 35 \\
\end{tabular}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/tablas/tabla-simple.png)
```

Para añadir líneas de división entre columnas, se introduce el carácter de barra vertical `|` entre las letras que definen la justificación de las columnas en el argumento obligatorio del entorno `tabular`. Mientras que para añadir líneas de división entre filas, se utiliza el comando `\hline` al principio de cada línea. Se insertarán tantas líneas divisorias como veces se introduzca el comando `\hline`.

**Ejemplo**

```latex
% CUERPO
\begin{document}
% Tabla con líneas divisorias de filas y columnas.
\begin{tabular}{|l|c|r|}
\hline
Nombre & Ciudad & Edad \\ 
\hline
\hline
María & Valencia & 22 \\
\hline
Juan & Madrid & 50 \\
\hline
Carmen & Barcelona & 35 \\
\hline
\end{tabular}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/tablas/tabla-delimitada.png)
```

El comando `\multicolumn{num}{col}{texto}` permite crear celdas que se extienden a lo largo de varias columnas, donde `num` es el número de columnas a ocupar, `col` es el carácter que define la justificación de la celda (`l`, `r` o `c`), y `texto` es el contenido de la celda.

También es posible utilizar el comando `\cline{n-m}` para dibujar líneas horizontales divisorias que no abarquen toda la fila, sino desde la columna `n` hasta la `m`.

**Ejemplo**

```latex
% CUERPO
\begin{document}
\begin{tabular}{lrrcrr}
\hline
 & \multicolumn{2}{c}{Enero} & & \multicolumn{2}{c}{Febrero}\\
\cline{2-3}\cline{5-6}
Ciudad & Ingresos & Gastos & & Ingresos & Gastos\\ 
\hline
Madrid & 2500 & 1750 & & 2600 & 1800\\ 
Barcelona & 2250 & 1500 & & 2400 & 1650\\ 
\hline
\end{tabular}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/tablas/tabla-multicolumna.png)
```