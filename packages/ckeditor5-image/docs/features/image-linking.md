---
title: Images
menu-title: Linking images
category: features-images
order: 60
---

{@snippet features/build-image-source}

## Linking images

The {@link module:link/linkimage~LinkImage} plugin adds support for linking images. Some use cases where this could be useful are:

* Linking to a high-resolution version of an image.
* Using images as thumbnails linking to an article or product page.
* Creating banners linking to other pages.

The image link can be added or edited via the image toolbar. An icon in top right corner of the image indicates the presence of a link.

```html
<figure class="image">
	<a href="...">
		<img src="..." alt="...">
	</a>
	<figcaption>Image caption</figcaption>
</figure>
```
Use the link icon in the image toolbar to access the edit options for links on image.

{@snippet features/image-link}

### Enabling image linking

The image linking feature is not enabled by default in any of the editor builds. In order to enable it, you need to load the {@link module:link/linkimage~LinkImage} plugin. Read more in the {@link features/installation Installation} section.

<info-box info>
	The {@link module:link/linkimage~LinkImage} plugin is available in the {@link api/link `@ckeditor/ckeditor5-link`} package.
</info-box>

