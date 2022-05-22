1. [STYLES] - Make sure to add transition style under general selector, not the
one with `:hover` - this way transition will work smoothly both ways.

GOOD example:
```scss
.box {
  color: gray;
  transition: color 0.5s, transform 0.5s;

  &:hover {
    color: aquamarine;
    transform: scale(1.2);
  }
}
```

BAD example:
```scss
.box {
  color: gray;

  &:hover {
    color: aquamarine;
    transform: scale(1.2);
    transition: 0.5s;
  }
}
```

2. [STYLES] - Be consistent with your margins - if you have many sections in a
   row, add margins either to the bottom or to the top so that it will be easier
   to identify how to position the next element
3. [BEM] - Check your BEM structure using BEM-linter (`npm run lint`) and
   [this list](https://mate-academy.github.io/fe-program/css/typical-bem-mistakes)
4. [BEM] - Make sure to follow BEM naming convention

GOOD example:
```html
<div class="product__rating">
  <div class="product__stars stars stars--4">
    <div class="stars__star star"></div>
    <div class="stars__star star"></div>
    <div class="stars__star star"></div>
    <div class="stars__star star"></div>
    <div class="stars__star star"></div>
  </div>
</div>
```

BAD example:
```html
<div class="product__rating">
  <div class="product__stars stars--4">
    <div class="star"></div>
    <div class="star"></div>
    <div class="star"></div>
    <div class="star"></div>
    <div class="star"></div>
  </div>
</div>

`stars--4` is a modifier of the `stars` block, but `stars` block does not exist in HTML;
`star` is another block, stars should be the elements of the `stars` block
```

5. [BEM & STYLES] - Don't add external styles (positioning or margins) to
   BEM-blocks. Use mix where necessary and move all external styles under element
   selector.

GOOD example
```html
<!--index.html-->
<div class="container">
  <div class="container__card card">
    ...
  </div>
</div>
```
```css
/*style.css*/
.container__card {
  margin: 48px 24px;
}

.card {
  font-size: 16px;
  background-color: purple;
}
```

BAD example
```html
<!--index.html-->
<div class="container">
  <div class="card">
    ...
  </div>
</div>
```
```css
/*style.css*/
.card {
  margin: 48px 24px;
  font-size: 16px;
  background-color: purple;
}
```
6. [SASS] - Make use of SASS nesting - write pseudo-class, pseudo-element
   selectors inside general selector. As well as media queries.

GOOD example:
```scss
&__buy-link {
  display: flex;
  margin-top: 20px;

  &:hover {
    color: blue;
  }
}
```

BAD example:
```scss
&__buy-link {
  display: flex;
  margin-top: 20px;
}

&__buy-link:hover {
  color: blue;
}
```

7. [SASS] - use variables for the main values so that you'll be able to reuse
    them and give them descriptive names. But don't overuse them, don't create
    variable for the value that's used just once.
