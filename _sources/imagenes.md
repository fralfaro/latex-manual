# Imágenes

Para incluir una imagen o figura en un documento, además de disponer de la imagen del fichero en un formato gráfico adecuado, es necesario cargar en el preámbulo el paquete `graphicx`. Este paquete permite gestionar imágenes en los formatos gráficos `jpg`, `png`, `tiff`, `eps` y `pdf` (los tres primeros son formatos de mapas de bits y los dos últimos vectoriales).

Una vez cargado el paquete, para insertar una imagen en el documento basta con utilizar el comando `\includegraphics[opciones]{fichero}`. Este comando tiene como argumento obligatorio es el nombre del fichero con la imagen (incluyendo la ruta en el sistema de ficheros local) y los siguientes argumentos opcionales para modificar el aspecto de la imagen:

- `height`: Indica la altura de la imagen. Escala la imagen hasta esa altura.
- `width`: Indica la anchura de la imagen. Escala la imagen hasta esa anchura.
- `scale`: Factor de escalado de la imagen de 0 a 1.
- `angle`: Ángulo de rotación de la imagen. Rota la imagen en el sentido de las agujas del reloj los grados indicados.

**Ejemplo**

```latex
% PREÁMBULO
\usepackage{graphicx}
% CUERPO
\begin{document}
Ejemplo de imagen en línea 
\includegraphics{img/logo-aprendeconalf.png}, 
escalada
\includegraphics[height=1cm]{img/logo-aprendeconalf.png},
y rotada
\includegraphics[angle=90]{img/logo-aprendeconalf.png}

Ejemplo de imagen centrada:

\begin{center}
\includegraphics{img/logo-aprendeconalf.png}
\end{center}
\end{document}
```

```{admonition} Salida
:class: dropdown
![](img/imagenes/imganes.png)
```
