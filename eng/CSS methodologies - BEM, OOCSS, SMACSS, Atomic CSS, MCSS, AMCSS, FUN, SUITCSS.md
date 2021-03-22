## CSS methodologies - BEM, OOCSS, SMACSS, Atomic CSS (ACSS), MCSS, AMCSS, FUN, SUITCSS

#### [BEM](https://en.bem.info)

The BEM (Block Element Modificator) methodology divides css into 3 parts:
- Block - an independent block that could be reused anywhere
- Element - a part of the specific block, can't be used without it
- Modificator - describes any states of a block or an element, can't be used without independently


#### [OOCSS](https://github.com/stubbornella/oocss/wikis)

The OOCSS (Object-Oriented CSS) methodology gives 2 ideas of css code organization:
- Separate structure and skin
- Separate container and content


#### [SMACSS](http://smacss.com)

The SMACSS (Scalable and Modular Architecture for CSS) methodology divides css into 5 parts:
- Base - base styles for body, input, button, etc. Mainly, tag or attributes selectors are used here
- Layout - styles for header, footer, sidebar, etc. For single elements per page
- Module - styles for blocks that could be reused per one page
- State - styles for states: active, focused, collapsed and so on
- Theme - theme styles: colors, font, etc.


#### [Atomic CSS](https://acss.io)

The Atomic CSS (ACSS) methodology says: use one class for each reusable property (like inline-styles, but with classes)


#### [MCSS](https://operatino.github.io/MCSS/en)

The MCSS (Multilayer CSS) methodology divides css into 4 parts:
- Foundation - reset styles
- Base - styles for components: buttons, forms, navigation blocks, etc.
- Project - styles for components from the previous layout, but with the "context": registration form, login button, sidebar menu, etc.
- Cosmetic - appearance styles, they can't contain position rules


#### [AMCSS](https://amcss.github.io)

The AMCSS (Attribute Modules for CSS) methodology is like BEM, but styles are written through `data-*` attributes and use attributes selectors in css


#### [FUN](https://benfrain.com/enduring-css-writing-style-sheets-rapidly-changing-long-lived-projects)

The FUN (Flat Utility Namespace) methodology principles are:
- F - flat hierarchy of selectors: it is recommended to use the classes to select items, avoid a cascade without the need, and do not use ids.
- U - utility styles: it is encouraged to create the service atomic styles for solving typical makeup tasks, for example, `w100` for` width: 100%;` or `fr` for `float: right;`
- N - name-spaced components: recommendation of adding namespaces for specifying the styles of specific modules elements. This approach will avoid overlapping in class names


#### [SUITCSS](https://suitcss.github.io)

The SUITCSS methodology describes component-based development like BEM or AMCSS, but with its own features


### Links

- [Methods to organize CSS](https://css-tricks.com/methods-organize-css)
- [Cases of CSS organization RUS](https://habr.com/ru/post/256109)
