# Referencias cruzadas

Otro de los puntos fuertes de $\LaTeX$ es la gestión de las referencias cruzadas, es decir, referencias a otras partes del documento, así como las notas a pie de página.

## Referencias cruzadas

Como se ha visto, muchos elementos de un documento están enumerados: capítulos, secciones, figuras, tablas, ecuaciones, teoremas, páginas, etc. Para poder referenciarlos, cada elemento debe tener asignada una etiqueta única. Para asignar una etiqueta a cualquier elemento numerado se utiliza el comando `\label{etiqueta}`. Este comando debe ubicarse justo antes o después del elemento que quiere etiquetar. 

Posteriormente, para hacer una referencia al elemento en otra parte del documento se utiliza el comando `\ref{etiqueta}`.

**Ejemplo**

```latex
% PREÁMBULO
\usepackage{amsmath}
\DeclareMathOperator{\sen}{sen}
\usepackage{amsthm}
\newtheorem{teo}{Teorema}

% CUERPO
\begin{document}
\begin{teo}\label{teo-trigo}
Para cualquier ángulo
$\alpha$ se cumple 
\begin{equation}\label{eq-trigo}
\sen(\alpha)^2 + \cos(\alpha)^2 = 1.
\end{equation}
\end{teo}

Ejemplo de referencia cruzada. La ecuación \ref{eq-trigo} del teorema 
\ref{teo-trigo} es una ecuación básica en trigonometría.
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/referencias-cruzadas/referencias-cruzadas.png)
```

## Notas a pie de página

Para insertar una nota a pié de página se utiliza el comando `\footnote{...}`.

**Ejemplo**

```latex
% CUERPO
\begin{document}
El logotipo de latex es $\LaTeX$.\footnote{Fue creado por Leslie Lamport.}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/referencias-cruzadas/nota-pie.png)
```