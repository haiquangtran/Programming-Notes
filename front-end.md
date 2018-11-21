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


## Telerik UI
- Telerik UI for ASP.NET MVC is a set of server-side wrappers that allows using Kendo UI widgets from C# or VB.NET Code. Telerik UI is for .NET, AJAX, MVC, Core, Xamarin, WPF etc.
- UI Framework: UI Controls for navigation, layout, data management and visualisation and more.
- Mobile support, leverages touch and adaptive mobile rendering, responsive capabilities and integration with Bootstrap. Supports v4 Bootstrap.
- Wrappers vs Widgets: from a client-side perspective, the vanilla HTML/JS Kendo UI widgets and their ASP.NET MVC wrappers (UI helpers) reprsent the same thing and provide the same capabilities.
- You can use Telerik UI for ASP.NET MVC helpers and vanilla Kendo UI widgets at the same time on the same page, if a specific scenario requires that.

## Kendo UI
- UI Component library for JS based web apps using jQuery, Angular, React, or Vue frameworks.
- For ASP project you can still use Kendo UI as it has a js wrapper for ASP but if you want to do customizations it would be easier to use Telerik UI
- https://docs.telerik.com/aspnet-mvc/getting-started/kendo-ui-vs-mvc-wrappers


