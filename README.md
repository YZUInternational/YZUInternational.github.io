# YZU International 
## For Contributors
- As claimed in the "About site" part, we welcome any people, no matter you are a student or you are a teacher, no matter you are international students or regualar students in YZU to contribute to our website.
- For developer who wants to use ways like pull requests, it is welcomed and it is as easy as doing a simple pull requests and we will check and update as quickly as possible.
- For people who are fear of doing the staff above, it is also welcomed to write letters to us. Write about the latest news or something you want to share, email us at zhouzhouhi@qq.com. We also plan to build a wechat official account platform and there is hopefully to be a new way to submit articles.
- The propagdating job is currently done only by us, that is, students working for the international center. It is welcomed for any form of support for our work.

## Table of contents
- [Last important thing: YAML front matter ("parameters" for a page)](#last-important-thing-yaml-front-matter-parameters-for-a-page)
- [Features](#features)
- [Creating a User Page vs a Project Page](#creating-a-user-page-vs-a-project-page)
- [Showcased users (success stories!)](#showcased-users-success-stories)
- [Advanced: local development](#advanced-local-development-using-docker)
- [FAQ and support](#faq-and-support)
- [Credits and contributions](#credits)

## Add your own content

use markdown file or html file

## Last important thing: YAML front matter ("parameters" for a page)

In order to have your new pages use this template and not just be plain pages, you need to add [YAML front matter](https://jekyllrb.com/docs/front-matter/) to the top of each page. This is where you'll give each page some parameters that I made available, such as a title and subtitle. I'll go into more detail about what parameters are available later. If you don't want to use any parameters on your new page (this also means having no title), then use the empty YAML front matter:

```
---
---
```

If you want to use any parameters, write them between the two lines. For example, you can have this at the top of a page:

```
---
title: Contact me
subtitle: Here you'll find all the ways to get in touch with me
---
```

You can look at the top of [`aboutme.md`](./aboutme.md) or [`index.html`](./index.html) as more examples.

**Important takeaway: ALWAYS add the YAML front matter, which is two lines with three dashes, to EVERY page. If you have any parameters, they go between the two lines.**    
If you don't include YAML then your file will not use the template.

## Features

### Mobile-first
**Beautiful Jekyll** is designed to look great on both large-screen and small-screen (mobile) devices. Load up your site on your phone or your gigantic iMac, and the site will work well on both, though it will look slightly different.

### Customizable

Many personalization settings in `_config.yml`, such as setting your name and site's description, changing the background colour/image, setting your avatar to add a little image in the navigation bar, customizing the links in the menus, customizing what social media links to show in the footer, etc.

### Allowing users to leave comments

If you want to enable comments on your site, Beautiful Jekyll supports either the [Disqus](https://disqus.com/) comments plugin, [Facebook](https://developers.facebook.com/docs/plugins/comments) comments, [Staticman](https://staticman.net) or [JustComments](https://just-comments.com). If any of these are set in the configuration file, then all blog posts will have comments turned on by default. To turn off comments on a particular blog post, add `comments: false` to the YAML front matter. If you want to add comments on the bottom of a non-blog page, add `comments: true` to the YAML front matter.

#### Disqus comments

To use Disqus, simply sign up to [Disqus](https://disqus.com/) and add your Disqus shortname to the `disqus` parameter in the `_config.yml` file.

#### Facebook comments

To use Facebook comments, create a Facebook app using [Facebook developers](https://developers.facebook.com/docs/apps/register), and add the Facebook App ID to the `fb_comment_id` parameter in `_config.yml`.

#### Staticman comments

To use Staticman, you first need to invite `staticmanlab` as a collaborator to your repository (by going to your repository **Settings** page, navigate to the **Collaborators** tab, and add the username `staticmanlab`), and then accept the invitation by going to `https://staticman3.herokuapp.com/v3/connect/github/<username>/<repo-name>`. Lastly, fill in the `staticman` parameters in the Staticman section of `_config.yml`. You may also choose a different Staticman instance other than `staticmanlab`.

Optional: You may want to configure a webhook to prevent old inactive branches (representing approved comments) from stacking up.  You can refer to [Staticman's documentation](https://staticman.net/docs/webhooks) for details.  Make sure to input the **Payload URL** according to your chosen `endpoint`.  For example, the default `endpoint` is `https://staticman3.herokuapp.com/v3/entry/github/`, so the corresponding **Payload URL** should be `https://staticman3.herokuapp.com/v1/webhook`.

#### JustComments

To use JustComments you first need to have an account. After you just need to copy the API key to the `just-comments` property in `_config.yml` file.

### Adding Google Analytics to track page views

Beautiful Jekyll lets you easily add Google Analytics to all your pages. This will let you track all sorts of information about visits to your website, such as how many times each page is viewed and where (geographically) your users come from.  To add Google Analytics, simply sign up to [Google Analytics](https://www.google.com/analytics/) to obtain your Google Tracking ID, and add this tracking ID to the `google_analytics` parameter in `_config.yml`.

### Sharing blog posts on social media

By default, all blog posts will have buttons at the bottom of the post to allow people to share the current page on Twitter/Facebook/LinkedIn.  You can choose to enable/disable specific social media websites in the `_config.yml` file. You can also turn off the social media buttons on specific blog posts using `social-share: false` in the YAML front matter.

### RSS feed

Beautiful Jekyll automatically generates a simple RSS feed of your blog posts, to allow others to subscribe to your posts.  If you want to add a link to your RSS feed in the footer of every page, find the `rss: false` line in `_config.yml` and change it to `rss: true`.

### Page types

- **post** - To write a blog post, add a markdown or HTML file in the `_posts` folder. As long as you give it YAML front matter (the two lines of three dashes), it will automatically be rendered like a blog post. Look at the existing blog post files to see examples of how to use YAML parameters in blog posts.
- **page** - Any page outside the `_posts` folder that uses YAML front matter will have a very similar style to blog posts.
- **minimal** - If you want to create a page with minimal styling (ie. without the bulky navigation bar and footer), assign `layout: minimal` to the YAML front matter.
- If you want to completely bypass the template engine and just write your own HTML page, simply omit the YAML front matter. Only do this if you know how to write HTML!

### YAML front matter parameters

These are the main parameters you can place inside a page's YAML front matter that **Beautiful Jekyll** supports.

Parameter   | Description
----------- | -----------
title       | Page or blog post title
subtitle    | Short description of page or blog post that goes under the title
tags        | List of tags to categorize the post. Separate the tags with commas and place them inside square brackets. Example: `[personal, self help, finance]`
bigimg      | Include a large full-width image at the top of the page.  You can either give the path to a single image, or provide a list of images to cycle through (see [my personal website](https://deanattali.com/) as an example).
comments    | If you want do add comments to a specific page, use `comments: true`. Comments are automatically enabled on blog posts; to turn comments off for a specific post, use `comments: false`. Comments only work if you enable at least one provider(diqus, staticman, just-comments) in `_config.yml` file.
show-avatar | If you have an avatar configured in the `_config.yml` but you want to turn it off on a specific page, use `show-avatar: false`. If you want to turn it off by default, locate the line `show-avatar: true` in the file `_config.yml` and change the `true` to `false`; then you can selectively turn it on in specific pages using `show-avatar: true`.
image       | If you want to add a personalized image to your blog post that will show up next to the post's excerpt and on the post itself, use `image: /path/to/img`.
share-img   | If you want to specify an image to use when sharing the page on Facebook or Twitter, then provide the image's full URL here.
social-share | If you don't want to show buttons to share a blog post on social media, use `social-share: false` (this feature is turned on by default).
use-site-title | If you want to use the site title rather than page title as HTML document title (ie. browser tab title), use `use-site-title: true`. When set, the document title will take the format `Site Title - Site Description` (eg. `My website - A virtual proof that name is awesome!`). By default, it will use `Page Title` if it exists, or `Site Title` otherwise.
layout      | What type of page this is (default is `post` for blog posts and `page` for other pages. You can use `minimal` if you don't want a header and footer)
js          | List of local JavaScript files to include in the page (eg. `/js/mypage.js`)
ext-js      | List of external JavaScript files to include in the page (eg. `//cdnjs.cloudflare.com/ajax/libs/underscore.js/1.8.2/underscore-min.js`). External JavaScript files that support [Subresource Integrity (SRI)](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) can be specified using the `href` and `sri` parameters eg.<br/>`href: "//code.jquery.com/jquery-3.1.1.min.js"`<br/>`sri: "sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="`
css         | List of local CSS files to include in the page
ext-css      | List of external CSS files to include in the page. External CSS files using SRI (see `ext-js` parameter) are also supported.
googlefonts | List of Google fonts to include in the page (eg. `["Monoton", "Lobster"]`)
gh-repo   | If you want to show GitHub buttons at the top of a post, this sets the GitHub repo name (eg. `daattali/beautiful-jekyll`). You must also use the `gh-badge` parameter to specify what buttons to show.
gh-badge  | Select which GitHub buttons to display, available options are: [star, watch, fork, follow]. You must also use the `gh-repo` parameter to specify the GitHub repo.

### Advanced features (including how to use a custom URL address for your site)

I wrote [a blog post](https://deanattali.com/2015/03/12/beautiful-jekyll-how-to-build-a-site-in-minutes/) describing some more advanced features that I used in my website that are applicable to any Jekyll site.  It describes how I used a custom URL for my site (deanattali.com instead of daattali.github.io), how to add a Google-powered search into your site, and provides a few more details about having an RSS feed.
This website is great and have many features that I referred to when I develop the YZUInternational.github.io [repidemicsconsortium.org/](https://www.repidemicsconsortium.org/) R Epidemics Consortium

## FAQ and support

If you need any help, I suggest heading over to the [Jekyll support forum](https://talk.jekyllrb.com/).

Beautiful Jekyll is actively used by thousands of people with wildly varying degrees of competency, so it's impossible to answer all the questions that may arise. Below are answers to a few very common questions. Most questions that I get asked are not directly related to this theme, and instead are more general questions about Jekyll or web development. Many such questions can be answered by reading the [Jekyll documentation](https://jekyllrb.com/) or with Google.

#### How do I change the number of posts per page OR the colour of the navigation bar OR the image in the navigation bar OR ...?

Beautiful Jekyll is built to be very customizable, and as such, many questions about "how do I change ..." can be answered by looking at the `_config.yml` file. The configuration file has many adjustable parameters to customize your site.

#### How do I add a favicon to my site?

Easy! Just place a valid `favicon.ico` (or another valid favicon image) in the root directory of your project. And then wait! It can take a while to update.

#### How do I move the blog to another page instead of having it on the home page?

The default style of Beautiful Jekyll is to feature the blog feed on the front page. But for many sites that's not the ideal structure, and you may want to have a separate dedicated page for the blog posts. To have the blog hosted on a different URL (for example at `<mysite.com>/blog`), copy the `index.html` file into a folder with the same name as the desired page (for example, to `blog/index.html`), and in the `_config.yml` file you need to add a parameter `paginate_path: "/<page name>/page:num/"` (for example `paginate_path: "/blog/page:num/"`).

#### What size do you recommend using for the `bigimg` photos?

Unfortunately, this is a no-answer! There isn't a one-size-fits-all solution to this, because every person will view your site on a different browser with different dimensions. Some browsers will have very wide aspect ratio, some will be narrower, some will be vertical (such as phones), different phones have different screens, etc. The image will always be centered, so the only tip I can give is that you should make sure the important part of the image is in the middle so that it'll always show. Other than that, every browser will show a different clipping of the image.

#### How do I use MathJax equations in my posts?

MathJax can be easily integrated into your website with a one-line addition. You can see [this discussion](https://github.com/daattali/beautiful-jekyll/issues/195) for more information.

#### My project page appear to be broken after a recent update!

In June 2019, some URL related settings have been adjusted to be more in-line with how Jekyll uses them officially. Project Page absolute links might appear to be broken if you haven't propagated all necessary changes to your local templates, or if you have created additional templates making use of old settings. If a link contains a duplicated project path component, this is most likely the cause. In summary:

| &nbsp; | Old behavior | New behavior |
| --- | --- | --- |
| `url` setting | `https://user.github.io/projectname` | (unset, GitHub auto detects) |
| `baseurl` setting | `/projectname` | (unset, GitHub auto detects) |
| Absolute link construction | `{{ site.url }}/your/path` | `{{ '/your/path' \| absolute_url }}` |
| Relative link construction | `{{ site.baseurl }}/your/path` | `{{ '/your/path' \| relative_url }}` |

## Known limitations

- If you have a project page and you want a custom 404 page, you must have a custom domain.  See https://help.github.com/articles/custom-404-pages/.  This means that if you have a regular User Page you can use the 404 page from this theme, but if it's a website for a specific repository, the 404 page will not be used.

- If there are many navigation bar links and avatar, some of the links may get partially hidden behind the avatar. 
