# Estructura de un documento

## Esqueleto básico para `pdflatex`

El esqueleto básico del código fuente de un documento en español para compilar con `latex` o `pdflatex` es el siguiente:

```latex
% CLASE
\documentclass[a4paper,10pt]{article}

% PREÁMBULO
% Paquetes
\usepackage[utf8]{inputenc}
\usepackage[spanish]{babel}
\usepackage[T1]{fontenc}

% Título, autor y fecha
\title{Título}
\author{Autor}
\date{Fecha}

% CUERPO
\begin{document}

\maketitle

% Resumen
\begin{abstract}
Resumen
\end{abstract}

% Tabla de contenidos
\tableofcontents

Contenido del documento

\end{document}
```

Antes de explicar las distintas partes de este esqueleto conviene mencionar varias cosas sobre la sintaxis de algunos elementos básicos:

- **Comandos**: Los comandos comienzan siempre por la barra invertida (backslash) `\`. En muchas ocasiones van acompañados de argumentos obligatorios que se escriben entre llaves `{...}` y opcionales que se escriben entre corchetes `[...]`. 
- **Entornos**: Los entornos, a diferencia de los comandos, son bloques de código sobre los que se aplica alguna acción, y están delimitados siempre por un comando de apertura `\begin{entorno}` y otro de cierre `\end{entorno}`.
- **Comentarios**: Al igual que en otros lenguajes del programación se pueden hacer comentarios en el código fuente que no serán interpretados por el compilador. Para ello se utiliza el símbolo de porcentaje `%` al comienzo del comentario.
- **Símbolos reservados**: Existe una serie de símbolos que están reservados para funciones especiales. 

    - `\`: Indica el inicio de un comando.
    - `$`: Declara el entorno matemático.
    - `{ }`: Inicia y finaliza un grupo.
    - `#`: Indica el número de un argumento en la definición de comandos.
    - `%`: Indica el inicio de un comentarios.
    - `&`: Separa elementos en una tabla o fórmula.
    - `^`: Escribe un superíndice.
    - `_`, Escribe un subíndice. 
    - `~`, Indica por dónde se puede partir una palabra al final de una línea.

Para que aparezcan estos caracteres en el documento final es necesario escribirlos en el código fuente precedidos por la barra invertida (`\$`, `\{`, `\}`, `\#`, `\%`, `\&`, `\^`, `\_`, `\~`) excepto la barra invertida que se escribe con el comando `\backslash`. 

A continuación se explican las partes del esqueleto anterior.

### Clase de un documento

La primera línea de un fichero con código $\LaTeX$ indica la clase de documento que se va a generar mediante el comando `\documentclass`. En el ejemplo aparece un argumento obligatorio que indica el tipo de documento que se desea crear, artículo (`article`), pero se pueden crear otros tipos de documentos como informes (`report`), libros (`book`) o cartas (`letter`). . Y también aparecen dos argumentos opcionales, `a4paper` que indica el tamaño de la hoja en el documento final (a4), y `10pt` que indica el tamaño base de la fuente utilizada en el documento (existe también `11pt` y `12pt`).

### Preámbulo

El preámbulo es la parte que va después de la clase y antes del comienzo del cuerpo del documento. En parte suele utilizarse para la carga de los paquetes de macros que se van a utilizar en el documento y la configuración del documento. En el ejemplo el preámbulo comienza con la carga de tres paquetes mediante el comando `\usepackage`: el paquete `inputenc` que permite definir la [codificación de los caracteres](https://es.wikipedia.org/wiki/Codificaci%C3%B3n_de_caracteres) del código fuente (conviene utilizar la codificación `utf8` sobre todo si se van a utilizar caracteres no ASCII); el paquete `babel` que permite definir el idioma del documento (`spanish`); y el paquete `fontenc` que especifique las codificaciones[^1] de las fuentes (`T1`).

A continuación, se suelen configurar algunos aspectos del documento como podrían ser los márgenes, encabezados y pies, el título, autor y fecha, y otras muchas posibilidades.

En el preámbulo también se pueden definir nuevos comandos $\LaTeX$ o redefinir los ya existentes.

### Cuerpo

Contiene el texto del cuerpo del documento y tiene que ir dentro del entorno `document`. Suele empezar con el comando `\maketitle` si se desea empezar el documento con el título, autor y fecha que se hayan definido previamente en el preámbulo, y le sigue el comando `\tableofcontents` que introduce la tabla de contenidos en el documento. Finalmente iría el texto en sí con el contenido del documento.

## Esqueleto básico para `xelatex`

Si se va a utilizar el compilador `xelatex` los paquetes del preámbulo cambian y deberían utilizarse los siguientes:

```latex
% Paquetes
\usepackage{fontspec}
\setmainfont{Times New Roman}
\usepackage{polyglossia}
\setdefaultlanguage{spanish}
```

El paquete `fontspec` permite definir las fuentes tipográfica que se desean utilizar en el documento final (por ejemplo `Times New Roman`), que debe estar instalada en el sistema donde se compile el documento, y el paquete `polyglossia` permite definir el idioma del documento.

En la {numref}`overleaf-documento-base` se puede apreciar el documento final 
que se obtiene tras compilar el código anterior con `xelatex` en Overleaf.

```{figure} img/estructura/overleaf-documento-base.png
---
align: center
name: overleaf-documento-base
---
Estructura básica de un documento.
```

[^1]: Una codificación de fuente es un mapeo de los códigos de caracteres a los glifos de la fuente que se utilizan para componer su salida.