---
layout: post
title: "Django with multiple settings files and PyCharm"
description: ""
category: "django"
tags: ["django", "pycharm"]
---
{% include JB/setup %}

Django projects by default have one `settings.py` file containing all the important project settings. However you very likely want different settings for development and different for production or testing. For example debug mode should never been turned on on production site.

I am personally very happy with the "multiple settings files" pattern which you can read more about [here](https://simpleisbetterthancomplex.com/tips/2017/07/03/django-tip-20-working-with-multiple-settings-modules.html) or Google it.

However for me the first time it was not _obvious_ how to configure PyCharm to use custom settings file in the `settings` directory instead of the expected default `settings.py` in the root folder of the site.

## So here is a little guide:

### First, you need to modify Run/debug Configuration(s)

That is the dropdown menu to the left of Run and Debug buttons.

After clicking select "Edit configurations..."

Here you can see section named "Environment" and you need to edit the first field "Environment variables" - just click on the icon on the right.

Use "+" button to add new variable. As a name use: `DJANGO_SETTINGS_MODULE` and for the value `[project name].settings.[filename without .py]`. 

So lets say I have project named "HumbleBlog" and I want to use `dev.py` settings file in the `settings` directory. My value for `DJANGO_SETTINGS_MODULE` would be `HumbleBlog.settings.dev`. Thats it :-) You project will now use this settings file.

### Second, you need to tell the built-in Terminal what to use

PyCharm comes with handy Terminal window for running commands like `manage.py` and others. But if you use multiple settings files, it won't work. 

You need to go to PyCharm Preferences and select Terminal in the window. Here in the Project Settings section you can see the same "Environment variables" setting. Simply repeat the steps above to set the variable `DJANGO_SETTINGS_MODULE` to your desired settings file.

Done!

--- 

_Hope this was helpful. If you have any feedback, comments feel free to get in touch._