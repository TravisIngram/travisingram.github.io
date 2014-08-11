---
title: Sublime Text - Editing Preferences
layout: post
tags: Sublime Text
---

## Sublime Text Preferences

[Sublime Text](https://www.sublimetext.com), while quite powerful, extensible, and customizable, isn’t very user friendly.  At least for those folks more accustomed to consumer focused applications.  The most obvious example is the lack of a preference pane.  To make changes to the look and feel of Sublime Text, users must manually edit the preference files.

And yes, that’s files, plural.

Sublime Text separates out the preferences into three main categories.

* Settings - Default
* Settings - User
* Syntax Specific - User

These settings files are essentially one big [JSON](http://en.wikipedia.org/wiki/JSON) object and must be formatted as such.  Sublime Text is expecting something that looks like this;

```json
{
  "preference_name": "string",
  "preference_name": 15,

  // Comments are also allowed, even though not supported in JSON
  "preference_name": true,
}
```
===

### User Settings

The `Preferences.sublime-settings - Default` file is best left alone.  It’s actually overwritten every time the application is updated which, given its beta status, might happen now and again.  So to avoid the chance of loosing your changes, it's best to simply add the settings you'd like to modify to the appropriate file.  And just in case you forget, there’s a friendly reminder at the top of the default file that states all user specific preferences should be placed in `Preferences.sublime-settings - User`.

The first time you launch this file, it’s empty.  There are numerous individual settings you could add but, unfortunately, the Sublime Text documentation leaves much to be desired.  So much so that they provide a link to the [Unofficial Documentation](http://sublime-text-unofficial-documentation.readthedocs.org/en/sublime-text-2/reference/settings.html).

I've included a few basic settings below.  They are pretty self explanatory.  If you find that you’re missing something specific, chances are a quick Google search will bring up the relevant setting.  Which you can then add, restart, and be good to go.

```json

{
  "bold_folder_labels": true,
  "font_face": "Monaco",
  "font_size": 12,
  "highlight_line": true,
  "highlight_modified_tabs": true,
  "ignored_packages": ["Vintage"],
  "indent_to_bracket": true,

  // Columns in which to display vertical rulers
  "rulers": [80],

  // The number of spaces a tab is considered equal to
  "tab_size": 2,

  // Set to true to insert spaces when tab is pressed
  "translate_tabs_to_spaces": true,

  // Set to true to ensure the last line of the file ends in a newline
  // character when saving
  "ensure_newline_at_eof_on_save": true,

  // Set to true to removing trailing white space on save
  "trim_trailing_white_space_on_save": true,

  "word_wrap": false
}
```

===

### Syntax-Specific Settings

Sublime Text allows you to maintain settings on a language by language basis.  This allows you to ensure that your `Python` files have 4 spaces of indention and your `Ruby` or `YAML` files, only 2.

In order to modify the syntax specific settings, either create and save a new file with the appropriate extension, `.rb` for example, or open an existing one.

With the file open and active, select the following option:

![ST Pref Selection](http://cl.ly/image/1X052V3n3q0B/Sublime_Text-Pref.jpg "Sublime Text Pref")

```
Sublime Text => Preferences => Settings-More => Syntax Specific-User
```
Sublime Text will open a new, blank document.  As before, you’ll need to type out or paste in the settings you’d like to have.  I typically add;

```json
{
    "tab_size": 2,
    "translate_tabs_to_spaces": true
}
```

If you want to add additional settings later on, simply repeat the process, remembering to save the file once you’re done.

===

There’s much more that can be done but this should at least get you started.  Feel free to ping me if you have any questions.  I’ll do my best to answer them.
