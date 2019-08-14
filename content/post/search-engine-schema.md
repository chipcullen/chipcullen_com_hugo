---
title: "An Intro Search Engine Schema"
date: 2019-07-30T08:12:10-04:00
draft: true
slug: "an-intro-to-search-engine-schema"
description: "What is schema, how does it help search engines understand your content, and how to add it to your site."
tags: []
custom_properties: []
---

## A Caveat

I feel a little weird writing this blog post, because of a few factors:

- I am _not_ a Search Engine Optimization (SEO) expert by any means. I've worked _with_ such experts, and respect their knowledge and ability, and won't pretend to be anything close.
- I've seen almost _no mention_ of this subject in my usual reading circles of web development blogs. Any information on this tends to be found exclusively in SEO blogs. But this seems so crucial that I'm surprised it hasn't come up more.

So, I don't know if I'm missing something, but I'm here to share something that I've learned about Schema data and it's impact on a website.

## What is Search Engine Schema?

Search engine schema is a blob of structured data that is added to individual web pages. That data is constructed in such a way that a search engine crawler can parse it, and get a better understanding about your content.

## Why should I care about Search Engine Schema?

If your site is primarily **content based** (as opposed to say, a single page app), and you care about getting traffic from search engines, **you should probably care**. This is one of the best ways that you can signal to search engines certain things about your content that they might not otherwise understand.

[To quote Google](NEEDLINK):

> NEEDQUOTE Adding this data may help increase the chances your content will appear in search results

I fully acknowledge that at the time of this writing, this blog doesn't include search engine schema. It should. I've implemented it at work, and have seen its impact. That is why I'm trying to share this with others.

## Okay, I'm listening. What does this look like?

The short version is that you add data into your page that isn't generally seen by normal users, but they could if they 'view source'd it.

There are two ways to introduce this data:

- A specially tagged **JSON object** that includes certain keys that search engines are looking for
- **Microdata** in the form of attributes that are added to individual pieces of markup

Google has [specified](need link) that it **prefers the JSON object approach**, but, depending on how your data is organized and the way you can retrieve it, it may not be possible to implement. Do what you can.

## Give me an example of a JSON object

When adding this data to a page, typically this JSON object will apply to that entire page, or URI. So, the first thing you need to consider is: _what kind of content is this?_

The reason is that depending on the _kind_ of content, there are different kinds of schema that you will need to include, if you want a search engine to understand your content well.

For instance, lets say you have a blog. You could add something like this:

```html
<!-- this would go somewhere in the <head> of an html document -->
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "NewsArticle",
    "headline": "An Intro Search Engine Schema",
    "dateModified": 2019-07-31T08:10:17-04:00,
    "datePublished": 2019-07-30T08:12:10-04:00,
    "image": "http://path/to/image.png"
  }
</script>
```

A few things to note:

- There is a special script `type` attribute - `"application/ld+json"`
- The `"@context": "https://schema.org"` indicates that this data follows the format laid out by <https://schema.org>
- The `"@type": "NewsArticle",` indicates that this is an article. There are several `@type`'s that Search Engines will understand. There is the list that Schema.org has, which is fairly long. However, Google only understands a subset of those `@type`'s - you can [see that list here](NEED GOOGLE URL).
- The article `@type` requires certain key/value pairs in order to be considered valid, at least by Google's estimation. They spell out the required keys here. As you consider the types of content you have, think about which supporting pieces of data you will have available to you.
- This must be **valid JSON** in order for it to be parsed correctly

### Another example,

Let's say, for a TV Show:

```html
<!-- this would go somewhere in the <head> of an html document -->
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "TVSeries",
    "description": "The 1980's, with monsters.",
    "genre": "Science Fiction Nostalgia",
    "image": "https://path.to.some/image.png",
    "name": "Stranger Things",
    "numberOfSeasons": "3",
    "containsSeason": [
      {
        "@type": "TVSeason",
        "name": "Season 1"
      },
      {
        "@type": "TVSeason",
        "name": "Season 2"
      },
      {
        "@type": "TVSeason",
        "name": "Season 3"
      }
    ]
  }
</script>
```
