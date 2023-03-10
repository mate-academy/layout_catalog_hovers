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
2. [BEM] - Check your BEM structure using BEM-linter (`npm run lint`) and
[this list](https://mate-academy.github.io/fe-program/css/typical-bem-mistakes-en)

3. [SASS] - Make use of SASS nesting - write pseudo-class, pseudo-element
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

4. [SASS] - use variables for the main values so that you'll be able to reuse
    them and give them descriptive names. But don't overuse them, don't create
    variable for the value that's used just once.
