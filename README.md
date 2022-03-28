# Vars

So, this is the repo for my style system, that consists of functions and mixins for scss, that can be easily used in other scss/sass document. 

Color scheme based of the one from Tailwind. Colors can be accessed via function:
```scss
cold,cool,gray,true,warm
red,orange,amber,yellow,lime,green,emerald,teal,cyan,
sky,blue, indigo, violet, purple, fuchsia, pink, rose
```

General form of color function call:
```scss
something: colorname($int, ?$alpha: 1)
```
Here `$int` - is intensity of the color and optional parameter `$alpha` controls opacity.
 
Also there are some special color functions that can be called `colorname-after()` or `colorname-before()` that returns previous or next complement of the color in palet.
For example: `cyan-after()` returns the same color as `blue()`.

Also there are some functions for containers (blocks with automatically managed width) that may be applied to any class via:
```scss
@include container-small;
@include container-medium;
@include container-large;
@include container-huge;
@include container-full;
```

Some special functions for grids:
```scss
@mixin grid($n: 12) {
    display: grid;
    grid-template-columns: repeat($n, 1fr);
}

@mixin grid-auto($min) {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax($min, 1fr));
}

@mixin span-h($n) {
    grid-row: span $n / auto;
}

@mixin span-v($n) {
    grid-column: span $n / auto;
}
```

And function for text gradient that can be called:
```scss
@include text-gradient($color1, $color2, ?$dir: 30deg)
```
