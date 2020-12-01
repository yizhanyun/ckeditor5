---
title: Images
menu-title: Base image support
category: features-images
order: 30
---

{@snippet features/build-image-source}

## Base image support

The {@link module:image/image~Image} feature adds support for plain images with just the `alt` attribute set. This translates to the following HTML:

```html
<figure class="image">
	<img src="..." alt="...">
</figure>
```

<info-box hint>
	This feature follows the markup proposed by the [Editor Recommendations](https://ckeditor.github.io/editor-recommendations/features/image.html) project.
</info-box>

You can see the demo of a WYSIWYG editor with the base image feature enabled below:

{@snippet features/image}

<info-box hint>
	The base image feature, unlike in CKEditor 4, does not support any user interface for inserting or managing images. Its sole purpose is to lay ground for other plugins (mentioned above) to build the target user experience. This pattern (composition of atomic features) is common for CKEditor 5 and allows the developers to build their own customized experience by implementing specific subfeatures differently.
</info-box>

## Image contextual toolbar

The {@link module:image/imagetoolbar~ImageToolbar} plugin introduces a contextual toolbar for images. The toolbar appears when an image is selected and can be configured to contain any buttons you want. Usually, these will be image-related options such as the text alternative button (a feature introduced by the base image plugin) and [image styles buttons](#image-styles).

See a demo of a WYSIWYG editor with the contextual toolbar enabled:

{@snippet features/image-toolbar}

The image toolbar is configured to contain the image text alternative button:

```js
ClassicEditor
	.create( document.querySelector( '#editor' ), {
		image: {
			toolbar: [ 'imageTextAlternative' ]
		}
	} )
```

## Image captions

The {@link module:image/imagecaption~ImageCaption} plugin adds support for image captions:

```html
<figure class="image">
	<img src="..." alt="...">
	<figcaption>A caption goes here...</figcaption>
</figure>
```

By default, if the image caption is empty, the `<figcaption>` element is not visible to the user. You can click the image to reveal the caption field and write one. See the demo below:

<info-box hint>
	You can change the placement of the image caption by setting [`caption-side`](https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side) in your {@link builds/guides/integration/content-styles content styles} for the `.ck-content .image > figcaption` style. Changing it to `caption-side: top` will display the caption above the image.
</info-box>

## Image upload

See the {@link features/image-upload Image upload} guide.

## Inserting images via source URL

Besides the ability to insert images by uploading them directly from your disk or via CKFinder, you can also configure CKEditor 5 to allow inserting images via source URL.

In order to enable this option, install the `ImageInsert` plugin and add the `imageInsert` button to the toolbar (it replaces the standard `imageUpload` button).

```js
import ImageInsert from '@ckeditor/ckeditor5-image/src/imageinsert';

ClassicEditor
	.create( document.querySelector( '#editor' ), {
		plugins: [ ... , ImageInsert ],
		toolbar: [ ... , 'imageInsert' ]
	} )
```

This will add a new **Insert image** dropdown in the toolbar. To open the panel and add the image URL, click the arrow next to the image button. Check the demo below to insert a new image via URL or update an existing image by selecting it, opening the dropdown panel and pasting a new URL.

{@snippet features/image-insert-via-url}

## Responsive images

Support for responsive images in CKEditor 5 is brought by the {@link features/easy-image Easy Image} feature without any additional configuration. Refer to the {@link features/easy-image#responsive-images Easy Image integration} guide to learn how to use the feature in your project.

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

The image linking feature is not enabled by default in any of the editor builds. In order to enable it, you need to load the {@link module:link/linkimage~LinkImage} plugin. Read more in the [Installation](#installation) section.

<info-box info>
	The {@link module:link/linkimage~LinkImage} plugin is available in the {@link api/link `@ckeditor/ckeditor5-link`} package.
</info-box>

