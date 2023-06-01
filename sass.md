# Sass 
Sass (Syntactically Awesome Style Sheets) is a preprocessor scripting language that is used to extend the functionality of CSS by being more efficient and maintainable stylesheets. Some of its features are variables, nesting, functions, and mixins. Sass code is written in a syntax similar to CSS but with the added benefits. SassScript is the scripting language itself.

<br>

## Install in React
• `npm install sass`

<br> 

## Strength
* Creating variables `$`
* Nesting
* Parent Selector `&`
* Placeholder Selectors `%`, `@extend`
* Partials `@import`
* Two types of Comments `// and /* */`
* Interpolations `#{}`
* List
* Mixins `@mixin`
* For `@for`


<br>

## SASS Format
`.sass` (indented)
```
$bg: #ff0000
body
  background: $bg
```
* No puncation and indent accordintly
* Meaningful white space

<br>

## SCSS
```
$bg: #ff0000;
body {
  background: $bg
}
```
`.scss` (Sassy)
* 100% CSS  compaitable
* Most popular

<br>

## Fundamentals

### Variables
```
$highlight: yellow;

h1 {
  $highlight: red;
  color: $hightlight;
}

p {
  color: $highlight;
}
```
* (Global) Top Level 
* (Local) Curly Braces 
> Shadowing: When Local variable has the same name as Global

<br>

#### Global Flag
```
h1 {
  $highlight: yellow !global;
}
```
* Redefines globals
* Not for new variables


<br>

#### Variable Names: Underscores vs Hyphens
In variables name `_` is the same as `-`
```
$primary-color: red;
$primary_color: yellow

h2 {
  color: $primary_color;
}
```

<br>

## Nesting
```
.container {
  padding: 5rem;

  h2 {
    color: white;
  }
}
```
• Extra line of code
• Since Sass is compiled, more nested, longer to generate.

<br>

## Partials
Create different files with different pieces of code.
```
/* _variable.scss */
$colormain: orange;
$colorsecondary: yellow;

/* _core.scss */
@use "variables"
body {
  background: variables.$colormain;
}

/* style.css */
@use "variables" as var;
@use core;
h3 {
  color: var.$colormain;
}
```
* underscore in front of name: this tells the prasers not complie to seperate CSS file.
* @use parameter => connect to different partials (no underscore, no extensions)
* namedspaced variables - variable.$colormain, refereing that this style came from a partials. `as` to create a shortcut.

<br>

## Parent Selector
Works with nested styles to choose the parent of the current class.
```
.button {
  padding: 10px;
  border-radius: 5px;
  background: #000;
  color: #333;

  /* Copy the code from parent and insert into .button:hover */
  &:hover {
    background: #ff0000;
  }

  /* Create a class .button-primary */
  &-primary {
    color: #00ff00;
  }
 
  /* .container .button */
  .container & {
    text-align: center;
  }
}

```
* `&`: Ampersand - copies codes from parent insert it into new style.


<br>

## Placeholder Selectors
Creates the following class using `@extend` without creating the Placeholder class.

```
%btn {
  background-color: #ffffff;
  color: black;
}

.button-primary {
  @extend %btn;
  background: red;
}

.button-secondary {
  @extend %btn;
  background-color: organge;
}
``` 
* starts with `%`
* using `@extend` to extrapolate


<br>

## Comment
```
/* Gets out putted to the compiles CSS */
// Doesn't render to the final
/* ! The excelmation point force publish the comment */
/* Can use Interpolation: #{$colorparimary} */

```

<br>

## Mixins
Simliar to JS functions.
```
@mixin .button($color: #333333) {
  background-color: $color;
  border-radisu: 5px;
}

.button {
  @include button
}

.button-main {
  @include button(#ff0000);
  color: yellow;
}
```
* `$color`: Parameters `#333333` is the default value 

<br>

## Interpolations 
```
#{$i}
```

## For 
```
// Create a list
$font-size: (3rem, 2.5rem, 2rem)

@for $i from i through length($font-size) {
  h#{$i} {
    font-size: nth($font-size, $i)
  }
}

/* Produce
h1, h2, h3
```
`1 through 10`: 1 - 10
`1 to 10`: 1 - 9

<br>

## List
* spaces, commas,
* Indexed at 1
* Negative Index (-1) last item in the array
* immutable, when an element is changed it creates a new array.

```
$array: first, second, third, "forth item";

$array: first second third "forth item";

$array: (first, second, third, "forth item")

$array: [first, second, thrid, "forth item"]
```

### List Methods
* `length($array)`: length of the array
* `nth($array, 2)`: 2nd item in the array
* `set-nth($array, 2, newValue)`: Set the 2nd item to the newValue
* `index($array,currentValue)`: get the index of the currentValue
* `append($array, newValue, comma | space)`: append a new value with comma or space
* `join($array, $array2, comma | space)`: join two array