# Colores: Los colores en CSS

<br>
 La mayoría las pantallas funcionan con un modo de color aditivo. La suma de RGB da como resultado un blanco.
 Tenemos varias formas de dar color en CSS
    
 *IMPORTANTE*: Recordad que existe el color "transparent"

## Varias formas de dar color en CSS

### RGB/RGBA

En el modo RGB tenemos tres canales (Red, Green, Blue) y tenemos 8 bits de color por canal, (cada bit tiene dos posibles valores 0 ó 1) lo que significa que tenemos 2^8 posibles valores, que van desde 0 hasta 255.
    
Esto nos da un total de 255 * 255 * 255 = 16.581.375 colores.
Su sintaxis es rgb(R,G,B)
Si ponemos todos los canales a 0 tendremos un negro puro y si los ponemos a 255 tendremos un blanco.
Para movermos por la gama de grises debemos poner los 3 canales con el mismo valor, si ponemos los 3 canales a 128 tendremos el gris puro.

El modo RGB nos da la opción de utilizar un cuarto canal que correspondería al canal alpha, es decir, la transparencia, y su valor va desde 0 a 1. Tenemos dos sintaxis para utilizar el canal alpha <br> 
      rgba(R,G,B,A)<br>
      rgb(R G B / A)


### HEXADECIMAL

La notación hexadecimal es la más común en desarrollo web, se basa en los mismos principios que el RGB pero escrito en notación hexadecimal. 

El sistema hexadecimal es un sistema basado en 16 valores del 0 al 15

Utiliza los dígitos del 0 al 9 y las letras de la A a la F
    
En este tipo de notacíon también necesitamos 256 valores.

Se compone de 16 caracteres en parejas ya que 16*16 = 256
<br>
0 1 2 3 4 5 6 7 8 9 A B C D E F<br>
0 1 2 3 4 5 6 7 8 9 A B C D E F<br>

Para indicar que vamos a usar notación hexadecimal debemos usar el símbolo de hash/almohadilla # y a continuación usaremos esta notación por parejas.

#RRGGBB<br>
Cuando una pareja usa el mismo valor se puede omitir el segundo valor, siempre que se haga en las 3 parejas.

rgb(255,255,255) -> #FFFFFF -> #FFF<br>
rgb(0,0,0) -> #000000 -> #000

También tenemos la opción de usar transparencias en hexadecimal añadiendo un cuarto canal que sigue las mismas normas.<br>
rgb(0 0 0 / .5) -> #00000080 ~> #0007

### HSL

El modo de color HSL es el más intuitivo para los humanos. Su nombre viene de las siglas Hue (tono) Saturation (saturación) y Lightness (luminancia)
    
El primer valor es el ángulo en el círculo cromático donde 0 y 360 será el color rojo. Hay ciertos valores que os pueden servir como referencia para relacionar mejor los colores con sus ángulos.

* 0 -> rojo
* 60 -> amarillo
* 120 -> verde
* 180 -> cyan
* 240 -> azul
* 300 -> magenta

![](https://mariobadilla.com/wp-content/uploads/2020/07/circulo.png)

El segundo valor es la saturación o intensidad del color.
* 0% -> gris
* 100% -> color puro

El tercer valor es la luminosidad del color:
* 0% -> negro, nada de luz
* 100% -> blanco, luz máxima

![](https://upload.wikimedia.org/wikipedia/commons/b/b9/HSL_color_solid_sphere_elliptical.png)

Nota: Es importante que aunque el valor de saturación o luminancia sea 0 hay que poner 0% si no, no funcionará
El modo HSL también admite transparencia y su sintaxis es la misma que la del modo RGB. Tenemos dos sintaxis disponible.

* hsla(h,s,l,a)
* hsl(h s l / a)
  
En ambos casos el valor alpha va de 0 a 1.

Existen otros cuatro modos de color en los que está trabajando que serían CMYK (Cyan, Magenta, Yellow y Black), HWB (Hue, Whiteness, Blackness), lab(Lightness, distance a, distance b) y lch(Lightness, chroma, hue), todos están en el borrador del modulo de color de nivel 4 pero aún no es estándar.

Hay tenéis ejemplos de su uso:

```css
body {
  background-color: mediumorchid;
  /* background-color: hsla(60 100% 50% / 0.5); */
}

.main {
  /* color: aquamarine; */
  /* background-color: currentColor; */
}

.box {
  /* border-top: 500px solid red;
  border-left: 250px solid transparent;
  border-right: 250px solid transparent; */
  width: 200px;
  height: 200px;
  background-color: lightcoral;
  /* background-color: rgba(0, 0, 0, 0.1); */
  /* background-color: rgb(0 0 0 / 0.3); */
  box-shadow: 5px 5px 10px rgb(0 0 0 / 0.5);
  box-shadow: 5px 5px 10px #0004;
  box-shadow: 5px 5px 10px hsl(180 50% 50%);
}
```

## ¿ Cómo elegir colores que combinen bien ?

Existen páginas que ya hacen este trabajo por nosotros, y en la actualidad existen varias, pero en un futuro seguro saldrán otras.

* [BrandColors.net](https://brandcolors.net/)
  Las paletas de color que utilizan las empresas famosas
* [Htmlcolorcodes.com](https://htmlcolorcodes.com/es/)
  Existen una tabla de colores, eligiendo y color y os dice que colores combinan bien.
* [Colorhunt.co](https://colorhunt.co/)
  Paletas completas que podeis elegir y todoas quedan bien entre sí.
* [Adoble colors](https://color.adobe.com/es/create/color-wheel) que es la opción más completa y os da una infinidad de posibilidades.