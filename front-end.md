# Front-end notes

## CSS Preprocessors
- Easy to write mixins, nestings, variables, and more.
- **Sass**
  - Sass uses Ruby (requires Ruby install)
  - Python-like syntax
  - More widely used than Less.
  - There are two syntaxes available for Sass.
    - **.scss(Sassy CSS)**
      - Extension of the syntax of CSS (every valid css stylesheet is a valid scss file with the same meaning)
      - Syntax is enhanced with the Sass features (mixins, variables etc)
    - **.sass (older syntax)**
      - Uses identation rather than brackets to indicate nesting of selectors, and newlines rather than semicolons to separate properties. 
      - Files using this syntax have .sass extension.
  - **LibSass**
    - library for Sass to support other languages (not just Ruby)
  - **Compass**
    - **No longer supported/maintained.**
    - A Sass framework
    - Provides you with helper functions, utility functions, mixins etc.
- **LESS**
  - Less uses Javascirpt. Less was constructed in Ruby, but has been ported to Javascript
  - To use LESS you upload applicable JavaScript files to your server or compile the CSS sheets through an offline compiler
- **Sass vs Less**
  - Both have similar features
  - Sass uses Ruby, Less uses JavaScript
  - Syntactical differences, Sass uses $ for variables, Less uses @.




