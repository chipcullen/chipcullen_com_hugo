---
title: "Migrating From Wordpress to Hugo"
date: 2018-09-13T21:22:49-04:00
draft: true
tags: [Hugo, Wordpress]
---

I wanted to share some of the experiences that I had migrating this blog from a Wordpress site to a Hugo site. This is more of a technical "how I did it" as opposed to [why I did it](/moving-to-hugo/).

## Background

After deciding to move to Hugo (after many years on Wordpress) it took some trial and error. I had about 120ish posts over 8 years of blogging. I had used a variety of text formats, code examples and imagery along the way.

## Getting content out of Wordpress

Per the [Hugo documentation site](https://gohugo.io/tools/migrations/#wordpress), there were (at the time) two options for migrating content out of Wordpress:

- _wordpress-to-hugo-exporter_ plugin for wordpress. I tried this first, as it seemed easiest. I just could _not_ get the plugin to work, no matter what I did. This roadblock actually stalled me for several months.
- _[blog2md](https://github.com/palaniraja/blog2md)_ which is a node package that is designed to parse the `.xml` file that Wordpress can export. Being that this involved `npm` installing it, I was very comfortable with this option. And, for the most part, **it worked**. This script wasn't originally available when I first attempted this, it seems to be a recent addition.

(There apparently is a 3rd python-based export option for Wordpress, but I have no experience with it.)

## Deciding what content to transfer

Now, I say my data export was _mostly_ successful, but there was one large hurdle:

My original Wordpress posts had largely already been authored in markdown. I think that the xml export, and cosequential blog2md parsing, didn't know what to do with that. So, my posts came over as large blobs of text that ran togehter.

I knew that I was going to have to manually clean up every post that I wanted to move over. It was at this point that [I decided to do a content inventory](/migrating-a-blog/) to remove low-value, or no-longer-relevant blog posts.

At the end of that, I knew that I had just over 50 blog posts that I was going to have to clean up, which was _much_ more approachable.

## Cleaning posts up

So, the blog text was already a big blob, but there were aspects of the data migration that had worked well. Specifically, the meta data block for each post was accurate.

Most critically, the URL's that I had ended up with for each post were correctly transferred as the filename for my posts.

After much trial and error, though, I found that the easiest solution for cleaning up a blog post file was probably the dumbest one: I would keep my Wordpress site open in my browser, and just copy & paste _that_ markdown into my new Hugo markdown files. It was the fastest way, and the least error prone. This only worked because I had already been authoring in Markdown for years.

## Moving images

Probably the biggest pain point in migration was dealing with images. Wordpress had inserted lots of absolute URLs to images that I had to manually copy over. Again, I did kind of a dumb obvious thing:

- I would copy the URL to a given image out of my blog post (copy & pasted as stated above)
- I'd open that URL in a browser
- I'd save _that_ image in a `/images/` directory
- Updated my blog posts to point to that image in markdown syntax

```markdown
![alt text for the image](../images/filename.png)
```

This relative URL is based on the assumption that my blog posts were not buried in a 'subdirectory' permalink structure.

Which leads me to …

## Dealing with URLs

One of my objectives was to make sure my existing blog posts would still be reachable at their existing URL's. That took some tweaking of the permalink configuration for Hugo.

It's pretty easy - this is what I ended up with in my `config.toml` file:

```toml
  [permalinks]
    post = "/:slug/"
```

Now, my files already had the correct names in terms of corresponding to urls (i.e. `/blog-post-url` and been recreated as `blog-post-url.md`), so I could have easily used:

```toml
  post = "/:filename/"
```

But I wanted to have an easy time adjusting URL's in future, and I figured manipulating metadata in the post front matter was an easier overall experience. So I had to add `slug` to all of my blog post files. That wasn't a big deal.

## Moving comments

used disqus, so if the URL lined up, comments showed up

## Monitoring 404's

following this blog post (link?) i created a google analytics report for every time a user ended up at a 404. i used this report to see if there was any critical content that i had some how screwed up
