# Secciones y párrafos

## Secciones y subsecciones

Normalmente un documento extenso se dividirá en secciones y subsecciones (o incluso capítulos si se trata de un libro). Para definir las secciones de un documento se utilizan los siguientes comandos:

- `\chapter{Título del capítulo}`. Crea un nuevo capítulo con el título indicado y lo numera. Solo puede usarse cuando la clase del documento es `book`.
- `\section{Título de la sección}`. Crea una nueva sección con el título indicado y la numera.
- `\subsection{Título de la subsección}`. Crea una nueva subsección con el título indicado y la numera.
- `\subsubsection{Título de la subsubsección}`. Crea una nueva subsubsección con el título indicado y la numera.

Las secciones definidas con estos documentos aparecerán en la tabla de contenidos automáticamente.

Existen versiones alternativas de estos comandos añadiendo un asterisco (`\chapter*`, `\section*`, `\subsection*`, `\subsubsection*`) que crean encabezados de sección sin numerar y que tampoco aparecerán in la tabla de contenidos.

**Ejemplo**

```latex
\documentclass[a4paper, 10pt]{article}
...
% CUERPO
\begin{document}
\tableofcontents

\section{Sección primera}
Texto de la sección.

\subsection{Subsección primera}
Texto de la subsección.

% Encabezado de subsección sin numerar
\subsection*{Subsección segunda}
Texto de la subsección.

\subsection{Subsección tercera}
Texto de la subsección.

\section{Sección segunda}
Texto de la sección.
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/secciones/secciones.png)
```



## Párrafos y cambios de línea

Para crear un párrafo nuevo basta dejar una o más líneas en blanco.

Si se quiere hacer un cambio de línea dentro de un mismo párrafo, se utiliza el comando `\newline` o `\\`.

**Ejemplo**

```latex
% CUERPO
\begin{document}
Este es el primer párrafo del documento, con un \\
cambio de linea.

Este es el segundo párrafo del documento. Obsérvese que cada vez que se 
comienza un párrafo la primera línea de desplaza un poco hacia la derecha. 
Esto se conoce como \emph{sangría}.
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/secciones/parrafos.png)
```


## Justificación

Los párrafos se justifican por defecto a la izquierda y a la derecha. $\LaTeX$ utiliza un algoritmo que permite partir las palabras al final de una línea para obtener párrafos con una buena estética (sin grandes espacios en blanco entre palabras). Pero también se pueden justificar solo a la izquierda, solo a la derecha o centrados entre los márgenes. Para ello se utilizan los siguientes entornos:

- `flushleft`: Justifica el texto a la izquierda.
- `flushright`: Justifica el texto a la derecha.
- `center`: Justifica el texto centrado entre los márgenes.

```latex
% CUERPO
\begin{document}
Este es el primer párrafo del documento, y aparece justificado a ambos lados
(márgenes izquierdo y derecho) por defecto. Para que las líneas tengan la 
misma longitud, se utiliza un algoritmo que permite partir las palabras al 
final de una línea.

\begin{flushleft}
Este es el segundo párrafo del documento y aparece justificado a la 
izquierda, es decir alineado con el margen izquierdo del documento. 
Obsérvese que no todas las líneas acaban a la misma altura.
\end{flushleft}

\begin{flushright}
Este es el tercer párrafo del documento y aparece justificado a la derecha,
es decir alineado con el margen derecho del documento. Obsérvese que no 
todas las líneas empiezan a la misma altura.
\end{flushright}

\begin{center}
Este es el último párrafo del documento y aparece justificado en el centro
entre los márgenes del documento. Obsérvese que ahora las líneas no 
empiezan ni terminan a la misma altura. 
\end{center}
\end{document}
```


```{admonition} Salida
:class: dropdown
![](img/secciones/justificacion.png)
```

`````{admonition} Advertencia
:class: warning
El algoritmo para partir palabras al final de una línea funciona muy bien, pero si alguna vez divide mal una palabra, se puede indicar por dónde partir la palabra con el comando `\-` (por ejemplo `si\-la\-ba`).
`````
