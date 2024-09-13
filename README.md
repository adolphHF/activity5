# Codigo modificado de memory.py (freegames)
 
Se añadió la funcionalidad de mostrar el total de taps en la pantalla, para lo cual también se modifico el tamaño de la ventana, haciendola más ancha.

Se añadio una sentencia para comprobar si todas las tiles pasaron su estado de hide a false, es decir, revisar que todas las tiles hayan sido reveladas.

## Centrar marcador en cuadro

Dentro de la función draw encontramos el código siguiente:

```python
if mark is not None and hide[mark]:
    x, y = xy(mark)
    up()
    goto(x + 11, y + 6)
    color('black')
    write(tiles[mark], font=('Arial', 30, 'normal'))
```

En este caso los valores que se le dan como parámetros a la función goto definirán la posición de nuestro marcador. En el ejemplo dado estamos aumentando 11 unidades hacia la derecha en x y 6 unidades hacia arriba en y. En caso de no tener una suma nuestro marcador se encontrará en la esquina inferior izquierda del recuadro.

## Cambiar marcador

Lo que se requiere para cambiar el marcador original, que representaba cada recuadro como un número, requerimos cambiar el arreglo tiles de la siguiente manera:

```python
tiles = ['😀', '😁', '😂', '🤣', '😃', '😄', '😅', '😆', '😉', '😊', '😋', '😎', \
 '😍', '😘', '😗', '😚', '🤗', '🤔', '😐', '😑', '🙄', '😏', '😮', '😯', '😴', '😛', \
 '😜', '😝', '🤤', '😒', '😓', '😔'] * 2
```

Lo que debemos tener en cuenta cuando cambiemos los valores es que el arreglo debe contener 32 marcadores diferentes y se multiplicará por 2 para que cada uno tengo una copia de sí mismo.
