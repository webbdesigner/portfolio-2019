---
layout: post
title:  "How is your website impacting the planet?"
date:   2021-03-27 17:46:28 -0400
categories: blog-post
meta: "People often think of the digital word of the internet as being up in the cloud(s). Although data may seem to be somewhat invisible, it’s not. Data is dirty and the electricity required to transfer it currently produces around 3.8% of global carbon emissions."
---



People often think of the digital word of the internet as being up in the cloud(s). Although data may seem to be somewhat invisible, it’s not. Data is dirty and the electricity required to transfer it currently produces around 3.8% of global carbon emissions. [If the Internet was a country, it would be the 7th largest polluter](https://www.nature.com/articles/d41586-018-06610-y) in the world. [231 million trees would need to be planted to deal with the pollution caused as a result of the data US citizens consumed in 2019.](https://gerrymcgovern.com/books/world-wide-waste/)

<hr>

## What can we do to combat our energy consumption on the web?

You’d be surprised to find that a lot of the same practices used for making your site more accessible, user friendly, and faster loading can be used to not only improve SEO but help make your site greener and more eco-friendly!

## Project management 💼

### Hosting

Before you start your next web project, it is important to consider where your site will “live”. Choosing a provider that uses renewable energy to power their servers and data centers is one of the easiest ways to reduce your site’s carbon footprint. [GreenGeeks, LLC](https://www.greengeeks.com/web-hosting), for instance, matches 3 times the amount of energy they consume from the grid in the form of renewable energy credits. This alone could make your website 300% more green!

Check out this [list of green energy hosting companies](https:/www.thegreenwebfoundation.org/directory) if you wish to learn more.  

### Create a [performance budget](https://developer.mozilla.org/en-US/docs/Web/Performance/Performance_budgets)

A performance budget is a list of goals created at the beginning of a project and is used to apply restrictions to [metrics](https://timkadlec.com/2014/11/performance-budget-metrics/) that can affect your sites performance. Like any budget, performance budgets are essential for operating at peak efficiency. Having a budget in place brings the web performance conversation to the front of the line and can be approached early on through all aspects of the design and build process. These set goals will help you make decisions while designing, choosing technology, and can point you towards better solutions throughout the process.

#### How to Budget:

- Study the competition. See how fast the largest competitor’s site loads and try to beat that.
- Or aim for load times for [Time-to-Interactive](https://calendar.perfplanet.com/2017/time-to-interactive-measuring-more-of-the-user-experience/) under 5s on 3G/4G and Under 170 KB of [critical-path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/) resources (compressed/minified)
- Skip the Javascript if you can. If you can’t, weigh the [cost of Javascript](https://v8.dev/blog/cost-of-javascript-2019) to your budget.

<hr>

## Content 📓

Performance should be at the forefront of everyone’s mind as they consider content for their next web project.

### [Search Engine Optimization (SEO)](https://moz.com/beginners-guide-to-seo)

Believe it or not, the goal of SEO is naturally aligned with reducing energy consumption. Optimizing your site helps the user find your information more quickly and results in them spending less time searching for the information. The less time a user spends searching Google, the smaller their carbon footprint!

### Copy writing

Like SEO, the copy (or page text) on your website affects the efficiency of the user’s experience. Your website’s information should be presented in a clear, concise, and logical format. This allows users to efficiently view your content and not waste their time trudging through a block of text that doesn’t offer any value to their experience or provide an answer to their initial query.

<hr>

## Design ✏️

### Use less font variations

Web font files can be a huge contributor to carbon emissions on the web. A single font file could weigh as much as 275kb! You can add another 250kb if you want it in bold. System fonts such as Times New Roman and Arial might not be as pretty, but they are already on the user’s device and don’t need any additional loading from the server.

> “Good design is as little design as possible.”
— Dieter Rams

### Use [Dark mode](https://css-tricks.com/a-complete-guide-to-dark-mode-on-the-web/) when you can

Allowing users to switch to a dark mode can help lower the light emitted by a user’s screen. Building a palette that utilizes a darker color scheme will use less energy on OLED screens.

### Use less [Raster images](https://www.printcnx.com/resources-and-support/addiational-resources/raster-images-vs-vector-graphics/#:~:text=Inherently%2C%20vector%2Dbased%20graphics%20are,limit%20for%20sizing%20vector%20images.)

Images are some of the largest files used on websites. Using a lot of images slows your site down and increases the amount of energy needed to run your it. It’s important to think about the images you will be using on your site. Does the image need to be large to convey the same information? Could we achieve the same effect with a vector graphic like an SVG or CSS?

When preparing raster image files for development, you should always [squoosh](https://squoosh.app/) your raster images down with tools like [TinyPNG](https://tinypng.com/) or [ShortPixel](https://shortpixel.com/) that can compress files without effecting quality. This could help bring the size of your images down significantly. The final step in curating small, quality raster images for your website is to save them as a [WebP](https://developers.google.com/speed/webp) instead of JPEG or PNG. WebP lossless images are around [26% smaller](https://developers.google.com/speed/webp/docs/webp_lossless_alpha_study#results) in size than PNGs!

### Build vector graphics with SVG and CSS

SVGs or Scalable Vector Graphics have small file sizes that compress well, can scale up to any size without losing quality, look great and can be controlled with CSS and JavaScript! They are great to use for logos, icons. and other graphics created in Illustrator or Figma.

<hr>

## Development 🛠️

### Load images at the right size

Don’t rely on CSS to resize your images to avoid loading images that are larger than what they will be displayed at. Take advantage of [the picture element.](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture)

{: .html}
```html
<picture>
	<source srcset="/images/image.webp" media="(prefers-color-scheme: dark)"/>
	<img class="image" src="/images/image.webp" alt="image alt"
	loading="lazy" decoding="async" />
</picture>
```

You can even use [AVIF images](https://jakearchibald.com/2020/avif-has-landed/) with the picture element for [browsers that can support it](https://caniuse.com/avif).

{: .html}
```html
<picture>
	<source srcset="/images/image.avif" type="img.avif" />
	<source srcset="/images/image.webp" media="(prefers-color-scheme: dark)"/>
	<img class="image" src="/images/image.webp" alt="image alt"
	loading="lazy" decoding="async" />
</picture>
```

Adding [loading=”lazy”](https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading) and [decoding=”async”](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decoding) will also help.

### Minify your assets.

[Minifying your CSS and JS](https://www.minifier.org/) reduces the file size by removing line breaks, spaces, comments, and other optimizations. Combining CSS into one file will reduce the amount of [HTTP requests.](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

### **Build a Static Site**

Dynamic websites are usually created with a CMS (content management system) such as [Wordpress](https://wordpress.org/) or [webflow](https://webflow.com/). A CMS will make queries to the website's database to dynamically generate pages. This causes a lot of work for the web server and therefore uses more energy. Static sites, on the other hand, will be generated as individual HTML files for each page with the help of a static site generator. There are many static site generators to choose from (I personally like [Jekyll](https://jekyllrb.com/) and [Eleventy](https://www.11ty.dev/)). These tools can help reduce your file sizes tremendously.

<hr>

## In Summary ⚖️

There are many ways to decrease the size of your web projects and to make them more eco-friendly. It is *our job* as builders of the web to make powerful, fast, inclusive technologies and take into consideration the impact these technologies have on our environment.

You can [check your site's carbon footprint here](https://www.websitecarbon.com/).

Thanks for listening 👋🏻
