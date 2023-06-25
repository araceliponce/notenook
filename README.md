# `NoteNook`      _(not nok)_


A combination of the words _"note"_ and _"nook"_.   
"Note" signifies written records or reminders, while "nook" evokes images of a cozy, tucked-away corner.   
Just like a nook in a room, NoteNook is a special place where you can tuck away your thoughts and ideas.


## Features

- Create notes with tags.
- Copy the content of notes with just a click.
- Edit and delete existing notes and tags.
- Filter your notes by tags and titles.
- Experience the masonry layout option in Firefox Nightly (with fallback layout for other browsers)

## Acknowledgements

NoteNook was crafted with love using the following technologies and libraries:

- React
- React DOM
- React Redux
- Vite
- Mantine library
- Custom CSS


## Planned Features

- [ ] Add toast notification to show when the note content has been copied successfully
- [ ] Implement the option to assign a background color to each tag using the tag ID
- [ ] Enable draggable functionality for the notes.
- [ ] Add the ability to export all the (visible?) notes at once.
- [ ] Add the ability to auto create multiple notes by uploading a text file or pasting content in textarea

## Curiosities

Hey there! In this section, I'll share one or two things I learned while making this app. 

Theres is one thing that is on top of my head, the Masonry layout. It took me a good two hours of work until I stumbled upon a surprisingly simple solution.

Instead of calculating heights for each note, setting the container height, messing around with divs to fill the gaps and more things I didn´t get to fully understand, I remembered something I had seen on Kevin Powell's channel. It's called the @supports rule. This little gem made all the difference in achieving the Masonry layout. It's not perfect, but it's pretty good, so now I'm including it here.

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
It is pretty simple but this snippet alone enables the glorious Masonry layout for browsers that support the grid-template-rows: masonry property. And! For other browsers, it gracefully fallbacks to a simpler layout by restricting the maximum height of the body of the note to a fixed height (I chose 15.4em because it's the one that looked the best to me).

I am thrilled by this discovery and wanted to share it as a curiosity.

That's all there is to it! Enjoy using NoteNook!
