---
title: Images
menu-title: Image basics
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

The {@link module:image/imagetoolbar~ImageToolbar} plugin introduces a contextual toolbar for images. The toolbar appears when an image is selected and can be configured to contain any buttons you want. Usually, these will be image-related options such as the text alternative button (a feature introduced by the base image plugin) and {@link features/image-styles image styles buttons}.

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

## Inserting images via pasting URL into editor

The {@link module:image/autoimage~AutoImage} plugin recognizes image links in the pasted content and embeds them shortly after they are injected into the document to speed up the editing. Accepted image extensions: jpg, jpeg, png, gif, ico.

<info-box>
	The image URL must be the only content pasted to be properly embedded. Multiple links (`"http://image.url http://another.image.url"`) as well as bigger chunks of content (`"This link http://image.url will not be auto–embedded when pasted."`) are ignored.
</info-box>

If the automatic embedding was unexpected, for instance when the link was meant to remain in the content as text, simply undo the action (by clicking the "Undo" button in the toolbar or using the <kbd>Ctrl/⌘</kbd>+<kbd>Z</kbd> keystrokes).

You can paste the image URL directly into the editor content, and it will be automatically embedded.

<input class="example-input" type="text" value="https://ckeditor.com/docs/ckeditor5/latest/assets/img/malta.jpg">

{@snippet features/image-insert-via-pasting-url-into-editor}

## Responsive images

Support for responsive images in CKEditor 5 is brought by the {@link features/easy-image Easy Image} feature without any additional configuration. Refer to the {@link features/easy-image#responsive-images Easy Image integration} guide to learn how to use the feature in your project.
