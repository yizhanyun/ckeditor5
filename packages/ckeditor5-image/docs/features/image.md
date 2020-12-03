---
title: Images
menu-title: Overview
category: features-images
order: 20
---

{@snippet features/build-image-source}

CKEditor 5 provides extensive support for images. All the important image-related features are available and the users can easily add images to the content ({@link features/image-upload using several convenient methods}), position and style the images easily. Each image can be separately resized, captioned and an alternative text can be provided, as well as a link using the image as an anchor.

See the styles employed to position images in the document, the captions and the image toolbar in the below example.

{@img assets/img/image-feature.png 775 The image feature with captions, styles and image toolbar in the CKEditor 5 WYSIWYG editor.}

The [`@ckeditor/ckeditor5-image`](https://www.npmjs.com/package/@ckeditor/ckeditor5-image) package contains multiple plugins that implement various image-related features. Check the documentation of each subfeature to learn more about it.

<info-box info>
	All features listed below except image resizing and image linking are enabled by default in all CKEditor 5 WYSIWYG editor builds.
</info-box>

Managing images from the editor:
* {@link module:image/image~Image} implements {@link features/image-base base support for images}.
* {@link module:image/imagetoolbar~ImageToolbar} adds the image feature's {@link features/image-base#image-contextual-toolbar contextual toolbar}.
* {@link module:image/imagecaption~ImageCaption} adds support for {@link features/image-base#image-captions captions}.
* {@link module:image/imagestyle~ImageStyle} adds support for {@link features/image-styles image styles}.
* {@link module:image/imagetextalternative~ImageTextAlternative} adds support for adding text alternative.
* {@link module:image/imageresize~ImageResize} adds support for {@link features/resizing-images resizing images}.
* {@link module:link/linkimage~LinkImage} adds support for {@link features/image-linking linking images}.

Adding images to the content:
* {@link module:image/imageupload~ImageUpload} adds support for {@link features/image-upload uploading dropped or pasted images}.
* {@link module:image/imageinsert~ImageInsert} adds support for {@link features/image-base#inserting-images-via-source-url inserting images via URL} and other custom integrations.

<!--
The all-features-included demo may go here, but we may decide on a better placement as well.
-->