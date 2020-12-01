---
title: Images
menu-title: Overview
category: features-images
order: 20
---

{@snippet features/build-image-source}

The [`@ckeditor/ckeditor5-image`](https://www.npmjs.com/package/@ckeditor/ckeditor5-image) package contains multiple plugins that implement various image-related features:

* {@link module:image/image~Image} implements [basic support for images](#base-image-support).
* {@link module:image/imagetoolbar~ImageToolbar} adds the image feature's [contextual toolbar](#image-contextual-toolbar).
* {@link module:image/imagecaption~ImageCaption} adds support for [captions](#image-captions).
* {@link module:image/imagestyle~ImageStyle} adds support for [image styles](#image-styles).
* {@link module:image/imagetextalternative~ImageTextAlternative} adds support for adding text alternative.
* {@link module:image/imageupload~ImageUpload} adds support for {@link features/image-upload uploading dropped or pasted images}.
* {@link module:image/imageinsert~ImageInsert} adds support for [inserting images via URL](#inserting-images-via-source-url) and other custom integrations.
* {@link module:image/imageresize~ImageResize} adds support for [resizing images](#resizing-images).
* {@link module:link/linkimage~LinkImage} adds support for [linking images](#linking-images).

<info-box info>
	All features listed above except image resizing and image linking are enabled by default in all CKEditor 5 WYSIWYG editor builds.

	Check the documentation of each subfeature to learn more about it.
</info-box>

## Demo

The all-features-included demo will go here.