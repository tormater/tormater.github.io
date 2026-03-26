---
title: Creating themes
---

## Setting up your theme

Creating a theme for Tormater Forum is simple! To start, you must create a folder for your theme, the name of which will be displayed on your forum dashboard. Inside this folder, you may include several elements of your theme, which are listed below.
* `style.css`: The CSS stylesheet for your forum theme.
* `icon.ico`, `icon.png`, and/or `icon.svg`: Favicons (the icon for a website which appears next to its title in the tab) for your forum theme. It is recommended to include all of these, however only one is required (the ico format has the most compatibility among browsers for favicons).
* `templates/`: See [Templates#In Themes]({{ "/wiki/tormater-forum/Templates#in-themes" | absolute_url }}).

## Using the forum color

The forum color (as configured by a forum admin) is provided to theme authors by means of CSS variables in the `:root:` pseudo-class. The exact color that the forum is set to is provided in the `--c-gradient-medium` CSS variable. Several modified (lighter and darker) versions are provided for convenience `--c-gradient-top`, `--c-gradient-bottom`, `--c-gradient-bottom-darker`, `--c-highlight`, and `--c-border`. 

The CSS code that the forum generates is shown below. Note that you want to include your own colors for this in your stylesheet as a default in-case there is no forum color selected.
```css
:root {
  --c-gradient-top: #00beef;
  --c-gradient-medium: #00beef;
  --c-gradient-bottom: #00beef;
  --c-gradient-bottom-darker: #00beef;
  --c-highlight: #00beef;
  --c-border: #00beef;
}
```
<small>'#00beef' is a placeholder color.</small>

## Using a default theme as a base

To use a default theme as a base for your stylesheet, you can import it into your `style.css` using the CSS `@import` directive like so:
```css
@import url("../Aurora/style.css");
```
