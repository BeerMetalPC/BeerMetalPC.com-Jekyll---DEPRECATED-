---
layout: post
title: BeerMetalPC.com
tags: [project, jekyll]
caption: Detailing my first foray into static sites, and the underlying services utilized.
description: >
  A high level explainer as to what services I was using before this site, why I built this one, and the design decisions made in the process.  
date: 11 Mar 2022
image: 
  path: /assets/img/projects/BeerMetalPC.com.png
  srcset: 
    1920w: /assets/img/projects/BeerMetalPC.com1920.png
    960w:  /assets/img/projects/BeerMetalPC.com960.png
    480w:  /assets/img/projects/BeerMetalPC.com480.png
links:
  - title: Jekyll
    url: https://jekyllrb.com/
  - title: Hydejack (theme)
    url: https://hydejack.com/
sitemap: false
---

* this unordered seed list will be replaced by the toc
{:toc}

## Why did I need a site? 

My need for a personal site arose out of frustration with commercial off the shelf offerings in 2022 and a desire for a personal project to obtain more happy brain chemicals. I've wanted a (semi-)professional looking site that could be associated with my public facing social media, directly host my own content without added crap to maintain like comments (ffs just [@ me on Twitter](https://twitter.com/BeerMetalPC)), and link through to my other public facing accounts. 

The habits formed by being raised in an inherently-frugal Pennsylvania Dutch family demanded something I could host for cheap, preferably free, and that I could spend near-zero time maintaining. Static sites came to mind by looking at the personal websites of several persons in infosec Twitter. ([@varcharr](https://twitter.com/varcharr)'s [How I Made my Website](https://casey.is/blogging/making-this-website/) was an immense help here) So far Jekyll seems to tick all the boxes. Cheap. Relatively easy to build and maintain. And still looks high quality. Did I mention cheap? 

### What's with the name? 

I have another unique handle I've used for online gaming purposes for years, but as I've started doing more public and professional interaction it became clear I needed another that was separate or at least at arms length from games. BeerMetalPC came about as a half-asleep showerthought: you've heard of a bare metal computer. What about beer metal? 🍺🤘💻. 

I've aligned most of my social media to this monicker, and had the BeerMetalPC.com pointed at other services. It's now associated to this site, and I've also pointed [FrankHelm.com](https://FrankHelm.com) here as a permanent redirect for the sake of consistency. 

### What was I using before? 

Previously I had made use of About.me, Linktree, and a couple others I've forgotten, but eventually settled on [Lnk.bio](https://lnk.bio/). Lnk.bio was easy to set up, used a wide variety of identity providers, had very good customizations, and had a reasonable one-time payment option for premium features rather than the subscription model most of their competitors use. I'd still recommend them if you need a personal links or landing page easy, cheap, and fast.

![image](/assets/img/projects/LnkBio.png){:.lead loading="lazy"}

My Lnk.bio page March 2022 prior to standing up this site.
{:.figcaption}

## Setup 
### Development
#### Offline Environment
I did most of this work on a 2021 Macbook Pro, M1 / Apple silicon. Admittedly this slowed my progress a bit as I was both learning macOS at the time, and having to fight my way through version weirdness to get all the necessary Ruby and Jekyll tools and dependencies installed. Once I was able to get both Ruby 3.0.x and Jekyll 4.2.x installed, I had some trial and error to get both Bundler and webrick installed and working. I'm including a few links below that I found helpful. 

- Youtube: [Install Jekyll on Apple Silicon (Jamstack)](https://www.youtube.com/watch?v=UKB9ylw0G4U)
- Jekyll forums: [Jekyll crashes on macOS Monterey](https://talk.jekyllrb.com/t/jekyll-crashes-on-macos-monterey/6673)
- Jekyll forums: [Jekyll crashing on M1 Mac](https://talk.jekyllrb.com/t/jekyll-crashing-on-m1-mac/6367?page=2)

I've done all of the first time setup and content creation locally, with Github Desktop for the commit to a private repo once v1.0 was ready to ship. 

#### Hydejack

[Hydejack](https://hydejack.com/) [Pro](https://qwtel.gumroad.com/l/nuOluY/qr0tw8m) stuck out as a gorgeous Jekyll theme with very good documentation, plus all the features I would need. Admittedly I could easily have gotten by on a free license, but I was jumping in with both feet and wanted to tinker with everything under the hood. Being able to start from Hydejack's prebuilt starter kit was an immense benefit. 

Hydejack, or perhaps Jekyll itself does have some frustrating quirks with how categories and tags are handled. Yes you can do some more granular sorting by categorizing posts and then sorting the tags, but at least for the time being this feels unnecessary for the small amount of content I have / will have. I'm proceeding with pretending that post categories feature does not exist. Similarly, Hydejack's projects feature has felt like just a blog post minus a few features, e.g. projects with tags don't display in a the tag page/collection. Again, using only tags has largely solved this problem, just make a tag for projects.

Google Fonts is disabled in _config.yml because I don't want to attest to explain anything in the Privacy Policy than I have to. If it causes privacy wailing and gnashing of teeth, and isn't serving a specific desired feature or function, bin it. 

I did learn the hard way that Jekyll can be ***very*** tempermental about spacing and alignment in the underlying Markdown files. Be deliberate. Work from templates.

##### Lazy Ren's Modifications

Another Hydejack user, Lazy Ren, made a blog post on [how they modified the Hydejack theme](https://lazyren.github.io/devlog/how-i-customized-hydejack-theme.html)  that links through to how to guides. Specifically, I made use of the [Applause button](https://lazyren.github.io/devlog/add-applause-button-for-jekyll-post), and the [Tags List page](https://lazyren.github.io/devlog/creating-tag-list-page). 

Applause worked out of the box and I would highly recommend it for other Hydejack users. But for the latter, because of my decision to only use tags, I had to remove every reference to categories and cut out the second nested loop in /_layouts/tags.html to get the featured_tags to display on the page semi-correctly. Not a huge problem, just another source of some trial and error; if you know what you're doing you can make the tags list prettier than the hatchet job I've done. 

Also: Ren's description of `type` might seems a big confusing. Go to /_featured_tags/ or /_featured_categories/ , in your tag/category .md files you need to add the text `type: tag` or `type:category` in order for the tag list page to be able to see and list those items.

#### Images

Going into this project I knew that I would handle images to either extreme depending on selected Jekyll theme. As Hydejack does an excellent job of presenting images, I had to do a little extra legwork in cropping, scaling, and optimizing images and assets. 

- [ImageCompressor.com / Optimizilla](https://imagecompressor.com/) has been my go to image compression and optimization service. 
- [Unsplash](https://unsplash.com/) for when I just need a free, good looking placeholder or banner. 

### Operations
#### Github

I took this project as a bonus opportunity to sit down and get truly familiar with [Github](https://github.com/). I completed some much overdue learning lab courses and capped it off with their [Github Pages](https://lab.github.com/githubtraining/github-pages) course which includes a tutorial on Jekyll. Although I'm hosting this site via Netlify, I'm still using Github to provide version control and CI. [Github Desktop](https://desktop.github.com/) made committing the entire project to a private repo easy, plus enforces version control locally so that my tinkering self doesn't hose the entire project. 

#### GoatCounter

[GoatCounter](https://www.goatcounter.com/) is a free for personal use analytics solution, easily implemented by just dropping a script tag in the_includes/my-head.html file, and it's privacy friendly to boot. Users can block GoatCounter by just adding gc.zgo.at to their firewall or adblocker blocklist. I get some basic site analytics, and head off a raft of privacy policy headaches. 

#### Netlify 

[Netlify](https://www.netlify.com/) provides the hosting and SSL, and integrates with Github so I can publish the site from a private repo. Don't know what else to say here than OAuth with Github, and go through selecting a repo and first time setup, it's really simple and straightforward. (Free tier is 100GB / mo in traffic, so we'll see how that holds up over time) 

Also, build command was `bundle exec jekyll build`, so don't panic if the default `jekyll build` isn't working. 

#### DNS

I use Google Domains as the registrar and DNS, but do so largely out of convenience. Use whatever you like. With everything stood up in Github and Netlify it was just a matter of delegating Netlify the domain, changing the DNS CNAME and NS records in Google domains, and waiting for the records to propogate. Netlify even automates the LetsEncrypt certificate generation. 

Admittedly the Google Domains interface does not make it obvious how to change NS records. You have to navigate to yourdomain --> DNS --> and then along the top ribbon of the DNS page select "Custom Names Servers." It is a part of the loaded view/page, not part of the bordering interface or blue text menus, if that makes sense. 

