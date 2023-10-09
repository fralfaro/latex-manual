# Listas

Existen tres tipos de listas, no ordenadas, ordenadas y descriptivas (en lugar de marcas o números los items de la lista están encabezados por texto), que se crean con los siguientes entornos:

- `itemize`: Crea un lista sin numerar.
- `enumerate`: Crea una lista enumerada.
- `description`: Crea una lista de tipo descripción.

Dentro de estos entornos, cada elemento de la lista debe empezar en una línea nueva con el comando `\item`. En el caso de las listas descriptivas, hay que proporcionar el texto del item de la lista como un argumento obligatorio.

**Ejemplos**

Ejemplo de lista no ordenada.

```latex
% CUERPO
\begin{document}
Ejemplo de lista no ordenada:
\begin{itemize}
\item Este es un item.
\item Este es otro item.
\item Y otro item más.
\end{itemize}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/listas/lista-no-ordenad.png)
```

Ejemplo de lista ordenada.

```latex
% CUERPO
\begin{document}
Ejemplo de lista ordenada:
\begin{enumerate}
\item Primer item.
\item Segundo item.
\item Tercer item.
\end{enumerate}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/listas/lista-ordenada.png)
```

Ejemplo de lista descriptiva.

```latex
% CUERPO
\begin{document}
Ejemplo de lista descriptiva:
\begin{description}
\item{\textbf{latex}} Genera documentos en formato dvi.
\item{\textbf{pdflatex}} Genera documentos en formato pdf.
\item{\textbf{xelatex}} Genera documentos en formato pdf que admiten 
codificación Unicode.
\end{description}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/listas/lista-desciptiva.png)
```

Se pueden crear sublistas anidando unos entornos dentro de otros.

**Ejemplo**

```latex
% CUERPO
\begin{document}
Ejemplo de listas anidadas:
\begin{enumerate}
\item Primer item.
    \begin{enumerate}
    \item Primer subitem.
    \item Segundo subitem.
    \end{enumerate}
\item Segundo item.
    \begin{itemize}
    \item Un item.
    \item Otro item.
    \end{itemize}
\end{enumerate}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/listas/listas-anidadas.png)
```


La indentación en el código fuente del ejemplo anterior no es obligatoria pero ayuda a ver mejor la estructura de anidamiento de entornos.
