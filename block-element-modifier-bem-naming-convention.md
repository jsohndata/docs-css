# CSS: Class Naming convention based on Block Element Modifer (BEM)

* Block: Standalone component on a page.
* Element: Part of that component. 
* Modifier: Variation or state of the component or element. 

Double underscores are used to indicate that an element is a part of a block.

```
/* Block */
.header {}

/* Element */
.header__logo {}
.header__title {}
.header__description {}

/* Modifier */
.header--small {}
.header__logo--small {}
```

In this example, "header" is the block, and "logo", "title", and "description" are elements. 

The double underscore in "header__logo" and "header__title" indicates that they are child elements of the "header" block. 

The double dash in "header--small", "header__image--rounded", and "card__title--bold" indicates that they are modifiers of the "header" block or its elements.





