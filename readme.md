# ANIMACIONES CON CSS

https://cssanimation.rocks/principles/

## Contadores en CSS

https://dev.to/cchana/explained-creating-a-zigzag-pattern-with-just-css-13g1

## Keyframe

```css
.class {
  animation-name: blink;
  animation-duration: 2s;
  animation-iteration-count: infinite;
}
@keyframes blink {
  0% {
    height: 6px;
  }
  10% {
    transform: translate(0px 3px);
    height: 1px;
  }
  20% {
    transform: translate(0px 0px);
    height: 6px;
  }
}
```

## Animation timing function, iteration count y delay

https://cubic-bezier.com/#.17,.67,.83,.67

## Animation direction, fill mode y play state

## CSS Triggers: layout, paint y composite

https://csstriggers.com/

JS => Style => Layout => Paint => Composite

### Rendimiento

- Composite: Ordena las partes de la página. Propiedades como opacity y transform.

- Paint: Rellena píxeles. Implica colores, imágenes, textos, sombras…

- Layout: Diseño de la página. Ancho, margin, padding, border…

### Debugging de animaciones con DevTools

En las devtools vamos a "More tools" => "Rendering" => "Frame rendering stats" checkeamos y veremos los fps = frames por segundo

Es recomendable que no pase de `60fps`

## Buenas practicas para optimizar animaciones web

Teniendo en cuenta lo que vimos en la clase de CSS Triggers, te dejo aquí 5 buenas prácticas para optimizar tus animaciones web:

- Usa dentro de lo posible propiedades que solo tengan que pasar por el proceso de Composite.
- Si necesitas animar alguna propiedad que sea muy costosa (como width, height, left, entre otras), trata de encontrar otra propiedad que sea menos costosa con la que puedas lograr el mismo resultado (o al menos un resultado similar).
- Evita animar muchas propiedades al mismo tiempo.
- Si necesitas esconder elementos, normalmente se usan las propiedades opacity y visibility en vez de usar la propiedad display (ya que es una propiedad no animable: [Propiedades que pueden ser animadas](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions#propiedades_que_pueden_ser_animadas)).
- Evita hacer animaciones que ocurran al hacer scroll, ya que el evento que escucha el scroll se ejecuta una gran cantidad de veces. Mejor espera a llegar a cierto punto de la pantalla y ahí ejecutas la animación.
