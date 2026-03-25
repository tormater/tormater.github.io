---
title: Creating extensions
---

## Setting up your extension
Create a folder with the name of your extension in `/extensions/` You can view the [default extensions](https://github.com/tormater/tormater-forum/tree/main/extensions) for an example.<br/>
Create a `manifest.json` formatted like so:<br/>
```json
{
 "title": "Extension Name",
 "author": "Your Name (supports BBCode)",
 "readme": "Extension Description (supports BBCode)",
 "supported_version": "cruiser-2.*" /* The forum version your extension is targeting */
}
```
Next, create a file named `extension.php`. This is where your extension's code will go.
## Using hooks to extend the software
Find a listener in the page you want to extend (and if there isn't one, you can make a pull request or an issue to add one), and use the `hook` function to hook your function into the listener. 
```php
hook("hookName","functionName");
```
If the hook that you'd like to use has arguments, you can access them using the `$args` array. For example:
```php
listener("beforeSaveConfig", $getArray, $array, $file);
```
`$getArray` can be accessed with `$args[0]`, `$array` can be accessed with `$args[1]`, and so on. Arguments to hooks are provided as references, so they can be modified within your extension.
## Adding pages 
If your extension needs it's own custom pages, it's easy to set them in your extension.  
In `extension.php`, add a line of code like so:
```php
$pages["my_custom_page"] = "extensions/extension_name/my_custom_page.php";
```
This will register a page at `/my_custom_page`, that goes to your PHP file, `my_custom_page.php`.

## Adding configuration
If your extension needs to be configurable through the admin panel, you can add a `settings` array to your extension's manifest.
```php
"settings": [
        {"id":"switch", "name":"Test Switch", "type":"bool", "default":"1"}
]
```
The `id` field determines the name you will use in your extension's code.

To access a setting through your extension, use the following code.
```php
$MyTormaterExtension = getExtensionName(__DIR__); // This ensures that the plugin works even when uploaded poorly.
echo $extension_config[$MyTormaterExtension]["switch"]; // "switch" is the id from above.
```
You may have noticed the `type` field, which controls the type of the setting in the panel.
There are currently 3 option types, which are listed below.

* `bool`: On/Off switch. Values: "0" or "1"
* `int`: Number input.   Values: Any numerical value
* `string`: Text input.  Values: Any text value (one line)
* `text`: Text input.    Values: Any text value (multi-line)
