# in_die-zine

See the site live at https://voenocturo.github.io/in_die-zine/

## Building/prerequisites

In order to build the site, you'll need ruby installed (I recommend installing with [`asdf`](https://asdf-vm.com/)), and some plugins.

```
gem install jekyll bundler jekyll-paginate jekyll-archives
```

Now you can build and view the site locally with

```
bundle exec jekyll serve
```

## Add a post

### Post requirements

In order to fit with the theme, all posts should have:

* A title
* An author
* A main image (this appears in the thumbnail link on the main page, and also at the very top of the post)
* (Optional) one or more "tags" for categorization
* (Optional) images in the post should be at least 840px wide
* (Optional) images in the post should have some alt text for accessibility

### File positions

First, you'll need to have your post in markdown format. Put this markdown in a file in `_posts` called something like `yyyy-mm-dd-title-without-special-characters.md` (e.g. `_posts/2022-03-22-the-world-building-chronicle.md`).

Second, all images for the post should be in their own folder in `assets/images`. Call this folder the same name as your post, so that it is easy to see which images go with which post (e.g. `assets/images/2022-03-22-the-world-building-chronicle.md`).

You can then reference the images in your post with something like

```
![here is the alt text]({{ site.baseurl }}/assets/images/2022-03-12-the-world-building-chronicle/image1.png)
```

### Converting from google doc

If the post is already in a google doc or word document, you can use an online converter like https://word2md.com/ to convert it, which works pretty well. It won't preserve images, but it will put in handy image placeholder markdown that is easy to replace with the real images.

To get the images from a google doc, you can go to File > Download > Web Page, unzip the resulting zip file, and there will be a folder with all of the images in it.

## References

This site uses the [Mediumish theme](https://www.wowthemes.net/mediumish-free-jekyll-template/).
