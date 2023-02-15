# A quick Hugo website
The purpose of this website is to illustrate the use of Hugo with the [LoveIt theme](https://github.com/dillonzq/LoveIt)

## Menu configuration

Edit the `config.toml` file:
```toml
[menu]
  [[menu.main]]
    name = "Posts"
    url = "/posts/"
```

`name` is the content of the menu button.
`url` is the path of the directory to which you're pointing.

## Directory structure

In the example above, the directory structure is as follows:
```sh
hugo-website-template
 |
 |- README.md
 |- config.toml
 |- content/
    |- posts/
 |- resources/
 |- themes/
 |- archetypes/
 |- data/
 |- layouts/
 |- static/
 |- public/
```

where the `url = /posts/` refers to:

```sh
content/
  |- posts/
```

## Compilation to HTML

The above configuration compiles to the following HTML:
```html
<div class="menu-inner">
  <a class="menu-item active" href="/posts/"> Posts </a>
  <span class="menu-item delimiter"></span>
  <a href="javascript:void(0);" class="menu-item theme-switch" title="Switch Theme">
    <i class="fas fa-adjust fa-fw" aria-hidden="true"></i>
  </a>
</div>
```

The important part being:
```html
<a class="menu-item active" href="/posts/"> Posts </a>
```

## How to create *markdown files* (not only posts):
```sh
hugo new posts/my-first-post.md
```

## Another example (in 3 steps)

Goal: have an About page

### Steps

1. Create an `about.md` file:
    ```sh
      hugo new about.md
    ```
    ```
      Content "/home/tux/tmp/hugo-website-template/content/about.md" created
    ```
2. Edit the file:
    ```md
      ---
      title: "About"
      date: 2023-02-15T19:12:59+01:00
      draft: false
      ---

      # Hi!
      My name is \<insert your name>, I like \<insert your hobbies>!

      I am also interested in \<stuff>.
    ```
    Remember, this is markdown, if you need help, check out: [https://www.markdownguide.org/](https://www.markdownguide.org/).

    Notice how we changed the `draft` to `false`, this is so that Hugo will build it.
    If you want Hugo to build draft pass `--buildDrafts` to `hugo server`:
    `hugo server --buildDrafts`
3. Edit the `config.toml` and add the following:
    ```sh
    [[menu.main]]
      name = "About me"
      url = "about"
    ```

    Look closely at the `url`, the specific page name doesn't have an extension.

## Detailed configuration

An example (self-explaining) `config.toml` can be found at:
https://github.com/dillonzq/LoveIt/blob/master/exampleSite/config.toml
