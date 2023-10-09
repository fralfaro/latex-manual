# Diseño de página

Existen distintos parámetros que determinan el aspecto final de una página con texto. En este capítulo veremos como modificar las dimensiones de la página, los márgenes, y cómo introducir encabezados y pies.

## Dimensiones y márgenes

Aunque es posible definir el tamaño de la página como un argumento del comando que define la clase del documento `\documentclass`, si queremos tener mayor control sobre las dimensiones del documento, así como de los márgenes, conviene utilizar el paquete `geometry`.

El paquete `geometry` permite definir las dimensiones de la página mediante un argumento opcional con distintos tamaños de página predefinidos (`a4paper`, `a5paper`, `b1paper`, `letterpaper`, etc.), pero también es posible definir nuestras propias dimensiones con los siguientes argumentos:

- `paperheight=x` establece la longitud vertical de la página en `x` (es necesario indicar las unidades `pt`,`mm` o `cm`)
- `paperwidth=x` establece la longitud horizontal de la página en `x`.

Por defecto la orientación del documento es vertical, pero puede ponerse en formato horizontal o apaisado con el argumento `landscape`.

**Ejemplo**

```latex
% PREÁMBULO
\usepackage[a5paper, landscape]{geometry}
\usepackage{blindtext}

% CUERPO
\begin{document}
\section{Introducción}
Esta es una página de tamaño A5 apaisada.

\subsection{Texto de relleno}
\blindtext[2]

\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/diseno-pagina/pagina-a5-apaisada.png)
```

También permite definir los márgenes del documento mediante los siguientes argumentos:

- `margin=x` establece los cuatro márgenes (izquierdo, derecho, superior e inferior) con tamaño `x` (es necesario indicar las unidades `pt`,`mm` o `cm`).
- `left=x` establece el margen izquierdo con tamaño `x`.
- `right=x` establece el margen derecho con tamaño `x`.
- `top=x` establece el margen superior con tamaño `x`.
- `bottom=x` establece el margen inferior con tamaño `x`.


**Ejemplo**

```latex
% PREÁMBULO
\usepackage[a4paper, left=2.5cm, right=3.5cm, top=45mm, bottom=20mm]{geometry}
\usepackage{blindtext}

% CUERPO
\begin{document}
\section{Introducción}
Este es una página con márgenes personalizados.
\subsection{Texto de relleno}
\blindtext[7]
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/diseno-pagina/pagina-margenes-personalizados.png)
```

## Encabezados y pies de página

$\LaTeX$ incluye encabezados y pies de página automáticos dependiendo del tipo de documento. Para las clases `article` y `report` no hay encabezado y el pie es el número de página, mientras que para la clase `book` el encabezado incluye la página y la sección a la que corresponde la página. No obstante, el usuario puede definir sus propios encabezados y pies mediante el paquete `fancyhdr`. 

Una vez cargado este paquete y antes de definir el texto del encabezado y del pie, hay que cambiar el estilo de página (`plain` por defecto) a `fancy`, y para ello se utiliza el comando `\pagestyle{fancy}` que indica al compilador que se van a usar un encabezado y pie personalizados.

A continuación hay definir el texto del encabezado y del pie. El paquete `fancyhdr` divide tanto el encabezado como el pie de página en tres areas (izquierda, centro y derecha) e incorpora comandos para escribir en cada una de ellas. El texto del área de la izquierda siempre se justifica a la izquierda, el del área del centro se justifica centrado y el del área derecha justificado a la derecha. Por otro lado, para documentos a doble cara, se distingue también entre encabezados y pies de páginas pares e impares. 

Para definir el encabezado y el pie de página se utilizan los comandos

-`\fancyhead[opcion]{texo}` añade el `texto` al encabezado de página en el area que se indique en el argumento opcional `opcion`, que puede ser `L` (área de la izquierda), `C` (área del centro) o `R` (área de la derecha), aunque para documentos a doble cara también se puede especificar el encabezado para páginas pares añadiendo una `E` o impares añadiendo una `O`.

-`\fancyfoot[opcion]{texo}` añade el `texto` al pie en el area que se indique en el argumento opcional `opcion`.


`````{admonition} Advertencia
:class: warning
El paquete `fancyhdr` no elimina los encabezados por defecto de cada tipo de documento, por lo que si se van a definir encabezados o pies personalizados, conviene utilizar los comandos `\fancyhead{}` y `\fancyfoot{}` para eliminar el encabezado y pie por defecto antes de definir los propios.
`````

**Ejemplo**

```latex
% PREÁMBULO
\usepackage{blindtext}
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhead{} % Borra el encabezado por defecto
\fancyhead[RO,LE]{\textbf{Mi encabezado}}
\fancyhead[C]{Alfredo Sánchez}
\fancyfoot{} % Borra el pie por defecto
\fancyfoot[LE,RO]{\thepage}
\fancyfoot[LO,RE]{\texttt{http://aprendeconalf.es}}

% CUERPO
\begin{document}
\section{Introducción}
Este es una página con encabezado y pie personalizado.

\subsection{Texto de relleno}

\blindtext[9]
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/diseno-pagina/encabezado-pie.png)
```

Como se puede observar, por defecto `fancyhdr` introduce una línea horizontal para separar el encabezado. Es posible modificar el grosor de la línea redefiniendo los comandos `\headrulewith` y `\footrulewith`. Por ejemplo, si no queremos que aparezca la línea se escribiría `\renewcommand{\headrulewidth}{0pt}`. 

Finalmente, el espacio entre el encabezado y el cuerpo del texto también se controla con el paquete `geometry` con la opción `headsep=x`. Del mismo modo, la separación entre el pie y el cuerpo se controla con la opción `footskip=x`. 


**Ejemplo**

```latex
% PREÁMBULO
\usepackage{blindtext}
\usepackage[top= 4cm, headsep=2cm]{geometry}
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhead{} % Borra el encabezado por defecto
\fancyhead[R]{\textbf{Mi encabezado}}
\fancyhead[C]{Alfredo Sánchez}
\fancyfoot{} % Borra el pie por defecto
\fancyfoot[R]{\thepage}
\fancyfoot[L]{\texttt{http://aprendeconalf.es}}
\renewcommand{\headrulewidth}{0pt}

% CUERPO
\begin{document}
\section{Introducción}
Este es una página con encabezado y pie personalizado.

\subsection{Texto de relleno}

\blindtext[9]
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/diseno-pagina/encabezado-pie-2.png)
```