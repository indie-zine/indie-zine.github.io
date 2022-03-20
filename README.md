# in_die-zine

See the site live at https://indie-zine.github.io

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

## Add an author

To add an author, you need to make changes to two places:

* On the About page, you need to add a new author card, and
* In the `_config.yml` file, you need to add the author metadata for posts

### About page author card

Edit the `_pages/about.md` file. There are two cards (`<div class="contributor card">`) per row, and for layout reasons every row must have two cards, though one may be invisible. If this is the first card in a new row, add a `<div class="card-deck contributors-row">` with two cards in it (just copy-paste some existing cards). Edit the first card with an appropriate title, role, and text, and add as many social links as you like in the `<div class="card-footer">` section (we have examples for twitter, instagram, and general web links).

If an invisible card is needed, use this template:

```
          <div class="contributor card" style="visibility:hidden">
            <div class="card-body">
              <h5 class="card-title">Title</h5>
              <p class="card-role">Role</p>
              <p class="card-text">Card text</p>
            </div>
            <div class="card-footer">
            </div>
          </div>
```

If the invisible card is no longer needed (you are adding a card that is the second in an existing row), simply remove the `style="visibility:hidden"` bit and fill out the card as needed.

### Author details in `_config.yml`

The section in `_config.yml` under `authors` needs a new section for each author who has written an article. Choose a name (this should be all lowercase, and is only used internally to identify the author of a post - it isn't shown anywhere on the site itself). You can add fields for name, display_name, avatar, gravatar, web, twitter, email, and description, and examples of all of these are present in the file. Everything except for name and display_name is optional.

If the author has an avatar, place it in the `assets/images/avatars` folder and reference it here under `avatar`.

Note that if you change the `_config.yml` file, these changes won't automatically update while you are running `bundle exec jekyll serve`. You'll need to use ctrl-c to stop the process and start it again to see those changes.
