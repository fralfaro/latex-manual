# Citas y referencias

Al igual que con las referencias cruzadas, $\LaTeX$ hace un maravilloso trabajo con las citas de referencias bibliográficas. Para ello se apoya en otro programa de gestión de referencias bibliográficas llamado [BibTeX](http://www.bibtex.org/), que viene incluido en la distribución estándar de $\LaTeX$. BibTeX permite crear una base de datos de distintos tipos de documentos que después se pueden citar en nuestro documento y después listar al final del documento las referencias bibliográficas citadas con diferentes formatos.

También existe otro gestor de referencias bibliográficas llamado `biber` que soporta la codificación de caracteres unicode, y por tanto es más apropiado si vamos a compilar nuestro documento con `xelatex`.

Para incluir referencias bibliográficas en un documento primero hay que crear una base de datos con las fuentes bibliográficas que vayamos a usar en un documento. Esa base de datos se crea en un fichero de texto independiente con el formato que requiere BibTex con extensión `.bib`. 

La sintaxis para crear una nueva entrada bibliográfica en la base de datos es un poco compleja al principio, pero afortunadamente existen bastantes aplicaciones de gestión bibliográfica, como [Zotero](https://www.zotero.org/), [Mendely](https://www.mendeley.com/), [EndNote](https://endnote.com/) o [RefWorks](https://refworks.proquest.com/researcher/) o [BibSonomy](https://www.bibsonomy.org/) que incluyen la posibilidad de exportar la bibliografía en ese formato.

**Ejemplo**

El siguiente fichero contiene una base de datos bibliográfica con dos entradas, un libro y un artículo de una revista.

```latex
% Fichero bibliografia.tex
@book{lamport_latex_1994,
	edition = {2nd},
	title = {{LaTeX}: {A} {Document} {Preparation} {System}, 2nd {Edition}},
	isbn = {978-0-201-52983-8},
	publisher = {Addison-Wesley Professional.},
	author = {Lamport, Leslie},
	month = jun,
	year = {1994}
}

@article{borbon_latex_2022,
	title = {{LaTeX}: {Primeros} pasos},
	journal = {Revista digital Matemática, Educación e Internet.},
	author = {{Borbón, Alexánder} and {Mora, Walter}},
	year = {2022},
	pages = {2--7},
}
```

Obsérvese que cada entrada bibliográfica empieza por el tipo de documento (book, article, etc.) y está descrita por varios campos: title (título), author (autor), journal (revista), year (año), etc. El primer campo es una clave que identifica al documento de manera única y que se utilizará posteriormente para citarlo.

Una vez creada la base de datos, para citar cualquier referencia contenida en ella, hay que cargar en el preámbulo el paquete `biblatex` e indicar la ubicación de la base de datos con el comando `addbibresource{bibliografia.bib}`, donde `bibliografia.bib` es el nombre del fichero con la base de datos bibliográfica (incluida la ruta), y luego escribir el comando `\cite{clave}`, donde `clave` es la clave de la entrada bibliográfica en la base de datos, en el lugar donde se quiera hacer la referencia.

Finalmente para listar las referencias bibliográficas citadas en el documento basta con insertar el comando `\printbibliography`.

**Ejemplo**

```latex
% PREÁMBULO
\usepackage{biblatex}
\addbibresource{bibliografia.bib}
% CUERPO
\begin{document}
El principal libro sobre latex es \cite{lamport_latex_1994}, aunque también 
es muy interesante el artículo \cite{borbon_latex_2022}

\printbibliography
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/bibliografia/bibliografia.png)
```

Existen diferentes estilos para las citaciones y para el listado con las referencias bibliográficas que se pueden indicar en la carga del paquete `biblatex` con el parámetro opcional `style`. Por ejemplo si en lugar de números en las citaciones queremos que aparezca las iniciales del autor y el año, hay que seleccionar el estilo `style=alphabetic`. En el siguiente enlace existe un listado exahustivo de los diferentes [estilos de citación](https://www.overleaf.com/learn/latex/Biblatex_citation_styles).

Por último si en lugar de `bibtex` se quiere usar `biber` para gestionar las referencias bibliográficas, hay que indicarlo también ebn la carga del paquete `biblatex` mediante el parámetro opcional `backend=biber`.

**Ejemplo**

```latex
% PREÁMBULO
\usepackage[
backend=biber, style=alphabetic]{biblatex}
\addbibresource{bibliografia.bib}
% CUERPO
\begin{document}
El principal libro sobre latex es \cite{lamport_latex_1994}, aunque también 
es muy interesante el artículo \cite{borbon_latex_2022}

\printbibliography
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/bibliografia/bibliografia2.png)
```
