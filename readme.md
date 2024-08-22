# Batman-Comic.CSS

`batman-comic.css` is a CSS utility-class library that allows to easily create Batman comics strips. Each character is 
a `<div>` that has the appropriate classes to show the character and their facial expressions.

## Characters

- Batman
- Robin

### Batman

Custom properties for colors:

- `--skin-color`: #fca (pink-ish)
- `--mouth-color`: #700 (dark red)
- `--suit-color`: #333 (gray)
- `--suit-color-dark`: #222 (dark gray)
- `--logo-color`: #ff5 (yellow)
- `--logo-color-dark`: #dd2 (dark yellow)
- `--eye-color`: #fff (white)

### Robin

Custom properties for colors:

- `--skin-color`: #fca (pink-ish)
- `--skin-color-dark`: #da8 (dark pink-ish)
- `--mouth-color`: #fff (white)
- `--suit-color`: #f00 (red)
- `--shirt-color`: #080 (green)
- `--cape-color`: #ff5 (yellow-ish)
- `--logo-color`: #ff5 (yellow-ish)
- `--logo-color-dark`: #000 (black)
- `--eye-color`: #fff (white)
- `--mask-color`: #000 (black)
- `--hair-color`: #000 (black)

---

## Character Expressions

All characters have these expressions available, add the classes and see how their faces change.

### Eyes

- `eyes-no`: No eyes.
- `eyes-think`: Eyes slightly closed from the top.
- `eyes-doubt`: Eyes slightly closed from top to bottom.
- `eyes-sad`: Eyes skewed to look sad (towards the inside).
- `eyes-angry`: Eyes skewed to look angry (towards the outside).
- `eyes-suspicious`: left eye think, right eye angry.
- `eyes-surprise` (combinable): larger eyes.
- `eyes-shock` (combinable): left eye smaller, right eye larger.

### Mouth

- `mouth-no`: No mouth.
- `mouth-sad`: Frawned mouth.
- `mouth-angry`: see mouth-sad.
- `mouth-talk`: Mouth with the character talking.
- `mouth-round`: a circle
- `mouth-whisper`: a small oval
- `mouth-right` (combinable): moves the mouth slightly to the right side.
- `mouth-left` (combinable): moves the mouth slightly to the left side.
- `mouth-to-right` (combinable): skews the mouth towards the right.
- `mouth-to-left` (combinable): skews the outh towards the left.

### Others

- `blush`: a redish glow in the visible part of the face.
- `scare`: a blueish glow in the visible part of the face.
- `shame`: a (lighter?) redish glow in the visible part of the face.

---

## Sizes and Positions

There are a series of classes that will apply to any element. These classes determine position and size of the element.

### Sizes

At this moment, you can only specify the width and an element, and it only applies to speech bubbles (you can use them on 
characters, but results may be disastrous). The class names will follow the pattern `.width-[AMOUNT]` where `[AMOUNT]`
is a multiple of 5:

- `.width-0`: a width of 0% of the container.
- `.width-5`: a width of 5% of the container.
- `.width-10`: a width of 10% of the container.
- ...
- `.width-100`: a width of 100% of the container.

### Positions

Positon must be specified using horitonzally and vertically with a series of classes that follow the pattern `.pos-[DIRECTION]-[AMOUNT]`:

- `[DIRECTION]` will be x or y for horizontal and vertical positioning respectively.
- `[AMOUNT]` will be a multiple of five that indicates the percentage to apply to the element (from the left of the panel).

By default, characters are positioned at the bottom part of the panel, so you won't need to specify the vertical position for them.

For example, if we want to place Batman at the center of the panel, we'll have to use the following code (50 being the center as it is 50%):

```
<div class="batman pos-x-50"></div>
```

### Rotations

You can use a set of generic classes to rotate elements withn certain limits (the rotations will apply to characters and props, too):

- `.rotate-0`: does not rotate the element (not really needed).
- `.rotate-5`: rotates the element 5 degrees clockwise.
- `.rotate-10`: rotates the element 10 degrees clockwise.
- `.rotate-15`: rotates the element 15 degrees clockwise.
- `.rotate-20`: rotates the element 20 degrees clockwise.
- `.rotate-25`: rotates the element 25 degrees clockwise.
- `.rotate-30`: rotates the element 30 degrees clockwise.
- `.rotate--5`: rotates the element 5 degrees counter-clockwise.
- `.rotate--10`: rotates the element 10 degrees counter-clockwise.
- `.rotate--15`: rotates the element 15 degrees counter-clockwise.
- `.rotate--20`: rotates the element 20 degrees counter-clockwise.
- `.rotate--25`: rotates the element 25 degrees counter-clockwise.
- `.rotate--30`: rotates the element 30 degrees counter-clockwise.

---

## Speech Bubbles

Speech bubbles are sections to write what the characters are saying or thinking. In this version, they are quite simple, 
they are some text and a line connecting the text to the speaking chracter.

```
<div class="bubble">Holy Interplanetary Yardstick, Batman!<div>
```

### Size

For speech bubbles sizes, check the previous section.

For the size of the line connecting the text with the character, there are a couple of classes that you could use to customize it:

- `short`: shorter line
- `tall`: longer/taller line

### Position

For speech bubbles positioning, check the previous section.

The line connecting text and character will be right-to-left by default. If you want to change direction and make it left-to-right, 
just add the `left` class... easy, no?

To move the line from one side to the other, we will use a class system similar to the one for horizontal positioning described on
the previous section, but indicating it is for hte line. For example, `pos-line-30` will place the line at a 30% from the beginning 
of the speech bubble.

### Off-panel Bubbles

Sometimes, we may want to have a speech bubble coming from a character located outside of the panel, that is not visible. In that 
case, add the off-panel class.

---

## Props

No props added yet.

---

## Panels

By default the comic strip is designed to have 3 panels per row, each panel taking a column within the row. But you can add classes 
to the section so they occupy different sizes. 

Add the classes `two`, `three`, or `four` to each panel so it spans two, three, or four columns respectively.

...But you can add the class `four-panels` to the comic strip so it will have four panels per row (they will be smaller, and the figures 
will be slightly scaled down.)

---

## "Best Practices"

To be determined. Something something "best practices don't work" something something. Just have fun for now. That should definitely 
be a best practice for this type of projects.

But if you want a set of best practices; here are some:

- Don't overlap elements/characters. It gets confusing.
- Add a role="img" and a hidden text description to your comics so they are slightly more accessible.

---

## Examples

### Example 1

```
<article class="batman-comic" role="img" aria-labelledby="batman-alt-0">
  <span id="batman-alt-0" class="visually-hidden">
    Comic strip with three panels showing Batman introducing himself, then someone off-panel asks if
    anyone has seen Bruce Wayne and a blushed Batman says that he has to go... for no reason in particular
  </span>
  <section>
    <div class="bubble pos-x-60 pos-y-5 width-70 short">Hi, I'm Batman! I fight crime and...</div>
    <div class="batman"></div>
  </section>
  <section>
    <div class="bubble pos-x-50 pos-y-5 width-90 off-panel left short">Hey! Has anyone seen Bruce Wayne?</div>
    <div class="batman blush mouth-no eyes-surprise"></div>
  </section>
  <section>
    <div class="bubble  pos-x-75 pos-y-5 pos-line-55 width-70">I must go... For no reason in particular...</div>
    <div class="batman blush mouth-to-left mouth-left mouth-round eyes-doubt"></div>
  </section>
</article>
```

### Example 2

```
<article class="batman-comic" role="img" aria-labelledby="batman-alt-1">
  <style>
    .batman {
      --suit-color: #dFa0aB;
      --suit-color-dark: #cF909B;
      --logo-color: #ff5;
      --logo-color-dark: #dd2;
    }
    .bubble {
      font-weight: 900;
      font-size: 2em;
    }
  </style>
  <span id="batman-alt-1" class="visually-hidden">
    Comic strip with an Batman wearing a pink suit angrily asking "Robin!! Did you wash your red shirt with my suit again?!?!"
  </span>
  <section class='three' aria-hidden="true">
    <div class="bubble pos-x-50 pos-y-10 pos-line-75 width-70 left">Robin!! Did you wash your red shirt with my suit again?!?!</div>
    <div class="batman pos-x-80 mouth-angry eyes-angry"></div>
  </section>
</article>
```

---

## Collaborations

Feel free to use the `batman-comic.css` library to create non-commercial comics. If you create a comic strip with this, please share 
it with me, you can find me on [Twitter](https://twitter.com/alvaro_montoro) or [Mastodon](https://front-end.social/@alvaromontoro).

Attribution is required (a comment in source code is fine).

---

## License

`batman-comic.css` is copyright 2024 by Alvaro Montoro.

The library is provided as-is. The author makes no representations or warranties of any kind, expressed or implied, as to the operation 
of the library, and is not responsible for any damage/side effect that the use of this library may cause.

