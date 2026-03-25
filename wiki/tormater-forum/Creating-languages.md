---
title: Creating languages
---

## Translating strings
To translate Tormater Forum, create a copy of `EN_US.php`, and rename it to your language's four letter code (for example, Spanish, Spain would be `ES_ES.php`).

Next, replace the values of the language array as shown below:
```php
"label.Draft" => "Draft",
```
```php
"label.Draft" => "Your translated language string.",
```
After that, just continue with all the language strings in the file, and then your language is complete.

## Creating a manifest
This section is optional, but if you want your language to have a proper name in the selector, create a json file with the same name as your language. (for example, if you were creating a manifest for `ES_ES.php`, it would be named `ES_ES.json`), and then fill it out as shown below:
```json
{
"name": "Español", 
"region": "España",
"region_abbr": "ES"
}
```
