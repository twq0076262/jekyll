# Assets
Jekyll provides built-in support for Sass and CoffeeScript. In order to use them, create a file with the proper extension name (one of `.sass`, `.scss`, or `.coffee`) and start the file with two lines of triple dashes, like this:

```
---
---

// start content
.my-definition
  font-size: 1.2em
```

## Sass/SCSS

Jekyll allows you to customize your Sass conversion in certain ways.

If you are using Sass `@import` statements, you’ll need to ensure that your `sass_dir` is set to the base directory that contains your Sass files. You can do that thusly:

```
sass:
    sass_dir: _sass
```

The Sass converter will default to `_sass`.

You may also specify the output `style` with the style option in your` _config.yml` file:

```
sass:
    style: :compressed
```

These are passed to Sass, so any output style options Sass supports are valid here, too.