---
title: Functions
---

## General purpose

```php
random_str(int $length)
```
Generates a random string of the specified length

```php
update_last_action(string $action)
```
Updates a user's last action to `$action`.

## Page generation

```php
parseAction(string $action, array $array)
```
Returns a name for a specific `$action`. Be sure to always use `$lang` as the second argument.

```php
genURL(string $page)
```
Returns a URL for a specific `$page`.
```php
message(string $content, $return=false)
```
Echoes or returns an HTML alert message with `$content` inside, depending on whether the second parameter is true or false.

```php
relativeTime(int $timestamp)
```
Returns relative time for a unix timestamp (example: 1 year ago).

```php
pagination(string $pageName)
```
Draws a page bar for the current page. `$pageName` controls where the buttons should link to.

```php
drawUserProfile(int $userid, int $type)
```
Draws a user's profile.

## Page control

```php
redirect(string $text)
```
Redirects to the specified page. (If left empty, defaults to the index)
```php
refresh(int $time)
```
Refreshes the current page, using `$time` as a delay.

## Authentication

```php
hashstring(string $text)
```
Takes a string as an input and hashes it using the forum's hashing algorithm.
```php
logout()
```
Logs the current user out.
```php
checkUsername(string $username)
```
Validates a username against a whitelist of characters.

## Configuration

```php
saveConfig(string $file, array $array)
```
Saves `$array` to `$file` as a configuration file.

```php
saveExtensionConfig(string $file, array $array)
```
Saves `$array` to `$file` as an extension configuration file.

## Hooks and listeners

```php
listener(string $hook)
```
Executes any functions hooked into the specified `$hook`.

```php
hook(string $hook, string $function)
```
Hooks a function into a listener.

## Captchas

```php
randomCaptcha(int $length)
```
Generates a random string of `$length` for use in the captcha.

```php
generateCaptcha(int $numChars)
```
Generates a captcha image of length `$numChars`.

## User control

```php
removeAvatar(int $userid)
```
Removes an avatar from a user.

```php
deleteUser(string $mode, int $userid)
```
Deletes a user. `$mode` can either be `deleteKeepPosts`, `deleteHidePosts`, or `deleteRemovePosts`.

## Limited usage

```php
hexAdjustLight(int $hex, int $percent)
```
Adjusts a hex color by `$percentage` lightness.




