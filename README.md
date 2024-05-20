# NoteNook      _(not nok)_

> "Note" signifies written records or reminders, while "nook" evokes images of a cozy, tucked-away corner.   
> Just like a nook in a room, NoteNook is a special place where you can tuck away your thoughts and ideas.

Aplicación web para tomar notas

Hecha usando React y TypeScript  

En cuanto a estilos usa:
- Mantine
- SCSS
  
En cuanto a implementaciones a destacar:
- Temas oscuro y claro
- Estilo mansory (con Firefox Nightly) con un fallback de alto definido
- Responsive layouts usando grid y flexbox.
- Puedes crear notas con título (opcional), contenido (requerido) y etiquetas (opcional, pero útil para buscarlas luego)
- Copia el contenido de cada nota dando un click derecho en la nota
- Filtra las notas por sus etiquetas y títulos

Curiosidades:  
Este fue el primer proyecto donde use la regla CSS `@supports` que vi en uno de los videos del experto en CSS: Kevin Powell.   
Muy útil para implementar el fallback en el caso de los navegadores que no soportan aún `grid-template-rows: masonry` :

```css

.is-masonry .nota__body {
  max-height: 15.4em;
}

@supports (grid-template-rows: masonry) {
  .is-masonry {
    grid-template-rows: masonry;
  }

  .is-masonry .nota__body {
    max-height: none;
  }
}
```
