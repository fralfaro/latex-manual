# Introducción

## ¿Qué es $\TeX$?

$\TeX$ es un sistema de composición de documentos de alta calidad, orientado especialmente a la creación de documentos científicos y técnicos que incluyen fórmulas matemáticas. Fue creado por [Donald Knuth](https://es.wikipedia.org/wiki/Donald_Knuth) en 1978.

A diferencia de un procesador de textos como por ejemplo Microsoft Word, $\TeX$ no es una aplicación sino un lenguaje de programación que requiere compilar el código fuente para obtener el documento final. Esto, que a priori podría parecer una desventaja, en realidad es la gran ventaja de $\TeX$ frente a los procesadores de texto que siguen el paradigma [WYSIWYG](https://es.wikipedia.org/wiki/WYSIWYG) (_What You See Is What You Get_), ya que permite separar fácilmente el contenido y la estructura de un documento, de su formato, de manera que el usuario puede centrarse en el contenido y la estructura del documento, y dejar que $\TeX$ se encargue del formato. De hecho, $\TeX$ incorpora un potente [lenguaje de marcado](https://es.wikipedia.org/wiki/Lenguaje_de_marcado) para estructurar y formatear el texto de un documento. Por ejemplo, mientras que para poner una palabra en negrita con un procesador de textos como Microsoft Word, bastaría con seleccionar la palabra y hacer clic en el botón de negrita para ver automáticamente la palabra en negrita en la pantalla del ordenador, en $\TeX$ habría que escribir en el fichero con el código fuente `{\bf palabra}` y después compilar el código fuente para obtener un documento final con la palabra en negrita (el comando `\bf`, que permite aplicar la negrita, se conoce como _marca_ o _tag_ en inglés).

La página principal con información sobre $\TeX$ es la del [TeX Users Group](https://www.tug.org/).

## ¿Qué es $\LaTeX$?

![Logo de LaTeX](img/logos/latex-project-logo.png)

$\LaTeX$ es un conjunto de macros para $\TeX$ debido originalmente a [Leslie Lamport](https://en.wikipedia.org/wiki/Leslie_Lamport) para facilitar el uso de $\TeX$.

Tanto $\TeX$ como $\LaTeX$ son programas de código abierto, liberados bajo la [licencia LPPL](https://www.latex-project.org/lppl.txt).

Otra de las grandes ventajas de $\LaTeX$ es que existen multitud de paquetes de código libre para generar distintos tipos de documentos que pueden descargarse desde el repositorio [CRAN](https://ctan.org/).

La página principal sobre $\LaTeX$ es [The LaTeX project](https://www.latex-project.org/).

## Instalación

Existen distintas distribuciones de $\LaTeX$ y algunas de ellas son multiplataforma, es decir, están disponibles para diferentes sistemas operativos. Las distribuciones más comunes son:

- [TeXLive](https://tug.org/texlive/) para Windows, Mac OSX y Linux.
- [MiKTeX](https://miktex.org/) para Windows, Mac OSX y Linux.
- [MacTeX](https://www.tug.org/mactex/) para Mac OSX.

En sus respectivas páginas está explicado el procedimiento de instalación de cada una.

Junto a la distribución de $\LaTeX$ es también habitual instalar algún editor de texto para escribir el código fuente. En realidad puede usarse cualquier editor de texto que ya esté instalado en nuestro sistema operativo, pero los existen entornos de edición especializados que facilitan muchas de las tareas del proceso de composición de documentos con $\LaTeX$. Los más comunes son:

- [TexMaker](http://www.xm1math.net/texmaker/). Es un editor de texto libre, multiplataforma, con muchos asistentes disponibles que permite previsualizar en tiempo real el documento final en pdf
- [Texstudio](http://www.texstudio.org/). Es otro editor libre y multiplataforma que incorpora aún más asistentes que el anterior. 
- [Vim](https://www.vim.org/) Es un editor de texto simple de propósito general que también es libre y multiplataforma. Incorpora paquetes o plugins específicos para facilitar la creación de documentos con $\LaTeX$. Especialmente indicado para trabajar desde la terminal.
- [Emacs](https://www.gnu.org/software/emacs/). Es otro editor similar a Vim, muy extendido entre los usuarios que prefieren usar la terminal.
- [Visual Studio Code](https://code.visualstudio.com/). Es un potente entorno de desarrollo multipropósito. Dispone de paquetes para los lenguajes de programación más comunes, entre ellos $\LaTeX$.

Pero también se puede empezar a componer documentos sin necesidad de instalar nada en el ordenador, usando un editor on-line como por ejemplo [Overleaf](https://www.overleaf.com/).

## Hola LaTeX

A modo de ejemplo, empezaremos por crear un sencillo documento con el texto "Hola $\LaTeX$".

Para ello utilizaremos nuestro editor de texto preferido para crear un fichero de texto con el nombre `main.tex` y el siguiente contenido:

```latex
\documentclass{article}
\usepackage[spanish]{babel}
\begin{document}
Hola \LaTeX
\end{document}
```


`````{admonition} Importante
:class: info
El nombre del fichero de texto con el código fuente de $\LaTeX$ puede ser el que queramos, pero es importante que la extensión sea `.tex`.
`````

Aunque más adelante se verá la estructura general del
código fuente de un documento en $\LaTeX$, a continuación se explica brevemente el contenido de este fichero:

1. En la primera línea se especifica el tipo de documento (`article`).
2. En la segunda línea se especifica el idioma del documento (`spanish`).
3. La tercera línea marca el comienzo del documento.
4. La cuarta línea contiene el texto del documento. `\LaTeX` es un comando que produce la salida $\LaTeX$.
5. La quinta línea marca el final del documento.

### Compilación

Para obtener el documento final hay que compilar el fichero fuente. Existen diferentes formas de hacerlo y en los editores anteriores suele ser tan sencillo como hacer clic en un botón o pulsar una combinación de teclas, pero en última instancia todos ellos hacen una llamada al compilador de $\LaTeX$ que es quien se encarga de convertir el código fuente en el documento final. 

Cada distribución de $\LaTeX$ viene con varios compiladores. Los más habituales son:

- `latex`: Es el compilador más antiguo y genera documentos en [formato `dvi`](https://es.wikipedia.org/wiki/DVI_(TeX)), que es un formato independiente creado mucho antes que el formato `pdf`.
- [`pdflatex`](https://www.tug.org/applications/pdftex/): Es el compilador más usado y genera documentos en formato `pdf`.
- [`xelatex`](https://tug.org/xetex/): Es un compilador más moderno que admite caracteres Unicode en el código fuente y el uso de tipografías más modernas.

En una terminal, la compilación de este documento sería tecleando el comando `latex main.tex`, `pdflatex main.tex` o `xelatex main.tex`, dependiendo del compilador que se quiera usar. A continuación se muestra la salida que general el compilador `pdflatex` al compilar el fichero `main.tex`.

```sh
> pdflatex main.tex 
s is pdfTeX, Version 3.141592653-2.6-1.40.22 (TeX Live 2021) (preloaded 
format=pdflatex) restricted \write18 enabled.
entering extended mode
(./main.tex
LaTeX2e <2021-06-01> patch level 1
L3 programming layer <2021-06-18>
(/usr/local/texlive/2021/texmf-dist/tex/latex/base/article.cls
Document Class: article 2021/02/12 v1.4n Standard LaTeX document class
(/usr/local/texlive/2021/texmf-dist/tex/latex/base/size10.clo))
(/usr/local/texlive/2021/texmf-dist/tex/latex/l3backend/l3backend-pdftex.def)
(./main.aux) [1{/usr/local/texlive/2021/texmf-var/fonts/map/pdftex/updmap/
pdftex.map}] (./main.aux) )</usr/local/texlive/2021/texmf-dist/fonts/type1/
public/amsfonts/cm/cmr10.pfb></usr/local/texlive/2021/texmf-dist/fonts/type1/
public/amsfonts/cm/cmr7.pfb>
Output written on main.pdf (1 page, 20106 bytes).
Transcript written on main.log.
```

En la figura {numref}`overleaf-hola-latex` se puede apreciar el documento
final que se obtiene tras compilar el código fuente en Overleaf.

```{figure} img/introduccion/overleaf-hola-latex.png
---
align: center
name: overleaf-hola-latex
---
Creación de un documento en Overleaf.
```

Al principio es muy habitual cometer errores en el código fuente, 
por lo que el proceso de compilación fallará. En ese caso es importante leer 
los mensajes de salida del compilador donde informará sobre el tipo de error y la línea donde se produjo el error, lo que facilitará su corrección. Algunos entornos de edición como por ejemplo Overleaf son capaces de anticiparse a los errores de compilación y detectan errores de sintaxis o gramaticales indicando el lugar exacto del error.

**Ejemplo**

Si en el documento anterior cambiamos el comando `\LaTeX` por otro que no existe, 
por ejemplo `\error`, al compilar el documento tendremos el siguiente error.

```sh
> pdflatex main.tex
This is pdfTeX, Version 3.141592653-2.6-1.40.22 (TeX Live 2021) (preloaded 
format=pdflatex) restricted \write18 enabled.
entering extended mode
(./main.tex
LaTeX2e <2021-06-01> patch level 1
L3 programming layer <2021-06-18>
(/usr/local/texlive/2021/texmf-dist/tex/latex/base/article.cls
Document Class: article 2021/02/12 v1.4n Standard LaTeX document class
(/usr/local/texlive/2021/texmf-dist/tex/latex/base/size10.clo))
(/usr/local/texlive/2021/texmf-dist/tex/latex/l3backend/l3backend-pdftex.def)
(./main.aux)
! Undefined control sequence.
l.6 Ejemplo de documento con un error. \error
                                             
? 
```

`````{admonition} Advertencia
:class: warning
Si el documento contiene referencias cruzadas, citaciones bibliográficas, tabla de contenidos o índices, es necesario compilar el documento dos o tres veces para que se generen automáticamente esas partes.
`````


