---
layout: post
title: BeerMetalPC.com
tags: [project, jekyll]
caption: Detailing my first foray into static sites, and the underlying services utilized.
description: >
  An high level explainer as to what services I was using before this site, why I built this one, and the design decisions made in the process.  
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

I have another unique handle I've used for online gaming purposes for years, but as I've started doing more public and professional interaction it became clear I needed another that was separate or at least at arms length from games. BeerMetalPC was half-asleep showerthought: you've heard of a bare metal computer. What about beer metal? 🍺🤘💻. 

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

[Hydejack](https://hydejack.com/) [Pro](https://qwtel.gumroad.com/l/nuOluY/qr0tw8m) stuck out a gorgeous Jekyll theme with very good documentation, plus all the features I would need. Admittedly I could easily have gotten by on a free license, but I was jumping in with both feet and wanted to tinker with everything under the hood. Being able to start from Hydejack's prebuilt starter kit was an immense benefit. 

I did learn the hard way that Jekyll can be ***very*** tempermental about spacing and alignment in the underlying Markdown files. Be deliberate. Work from templates.

#### Images

Going into this project I knew that I would handle images to either extreme depending on selected Jekyll theme. As Hydejack does an excellent job of presenting images, I had to do a little extra legwork in cropping, scaling, and optimizing images and assets. 

- I'm comfortable working in [GIMP](https://www.gimp.org/) so that's where I did most of my own image editing. 
- [ImageCompressor.com / Optimizilla](https://imagecompressor.com/) has been my go to image compression and optimization service. 
- [Unsplash](https://unsplash.com/) for when I just need a free, good looking placeholder or banner. 

### Operations
#### Github

I took this project as a bonus opportunity to sit down and get truly familiar with [Github](https://github.com/). I completed some much overdue learning lab courses and capped it off with their [Github Pages](https://lab.github.com/githubtraining/github-pages) course which includes a tutorial on Jekyll. Although I'm hosting this site via Netlify, I'm still using Github to provide version control and CI. [Github Desktop](https://desktop.github.com/) made committing the entire project to a private repo easy, plus enforces version control locally so that my tinkering self doesn't hose the entire project. 

#### Netlify 

[Netlify](https://www.netlify.com/) provides the hosting and SSL, and integrates with Github so I can publish the site from a private repo. Also provides analytics.

#### Google Domains

I use Google Domains as the registrar and DNS, but do so largely out of convenience. Use whatever you like. With everything stood up in Github and Netlify it was just a matter of providing Netlify the domain, and changing the Google Domains DNS records according to Netlify's instructions. 