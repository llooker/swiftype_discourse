# What this file does
This is a simple replacement for the `application.html.erb` file located at `/var/www/discourse/app/views/layouts/application.html.erb` which allows for Swiftype to better crawl the pages on Discourse.

# How to use this file
When using the [discourse/discourse\_docker](https://github.com/discourse/discourse_docker) application to manage your Docker container(s), you can use the following custom command to replace the `application.html.erb` file each time the image is rebuilt:

```
- exec: wget https://raw.githubusercontent.com/llooker/swiftype_discourse/master/application.html.erb -O /var/www/discourse/app/views/layouts/application.html.erb
```

This will download the file in this repository and overwrite the original `application.html.erb` file. In the future, it might be wise to replace this method with a find-and-replace command or script to supplement the existing `<meta name="description"` HTML tag with `class="swiftype"` and `data-type="string"`, which is the only difference between the original file and the one this is meant to replace.

If this doesn't work or breaks in the future, please blame Maxie Corbin (@maxcorbin).
