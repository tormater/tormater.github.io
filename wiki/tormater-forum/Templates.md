---
title: Templates
---
> Notice: Templates have not been fully implemented in the software yet. Some features may not work as intended.

Templates are HTML documents, with no content, to serve as a basis for the forum's pages.  
Templates use special symbols to tell the forum what to replace. Most templates have a data array, which replaces `[[ NAME ]]` with the value of `NAME` in the array. Templates can also load specific other templates, such as the header or footer.   
To do this, use `[[ #header ]]` or `[[ #footer ]]`.  
You can also use a subset of global variables in your template, by using `[[ $variable ]]`.
The available global variables are:
 - `forumName`
 - `forumTheme`
 - `forumDescription`
 - `forumFooter`
 - `baseURL`

To render a template, from a page, use the `$template` object's method, `render`.
```php
class Template
{
    function render($path, $strings)
}
```
`$strings` is a keyed array that is used to replace symbols with, and `$path` is the path to the template.

## Example

```php
$data = array(
	    "text" => "Example text.",
);

echo $template->render("templates/template_example.html", $data);
```
`template_example.html`:
```html
<html>
  <body>[[ text ]]</body>
<html>
```
## In themes
You can override default templates in skins by adding them to a `templates/` folder inside the theme.<br>
For example, if you wanted to override `templates/header/header.html`, you would place it in `/themes/YourThemeName/templates/header/header.html`.
