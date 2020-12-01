---
title: Images
menu-title: Installation
category: features-images
order: 70
---

{@snippet features/build-image-source}

## Installation

To add image features to your rich-text editor, install the [`@ckeditor/ckeditor5-image`](https://www.npmjs.com/package/@ckeditor/ckeditor5-image) package:

```plaintext
npm install --save @ckeditor/ckeditor5-image @ckeditor/ckeditor5-link
```

Next add the plugins that you need to your plugin list. You also need to set the desired image toolbar items.

```js
import Image from '@ckeditor/ckeditor5-image/src/image';
import ImageToolbar from '@ckeditor/ckeditor5-image/src/imagetoolbar';
import ImageCaption from '@ckeditor/ckeditor5-image/src/imagecaption';
import ImageStyle from '@ckeditor/ckeditor5-image/src/imagestyle';
import ImageResize from '@ckeditor/ckeditor5-image/src/imageresize';
import LinkImage from '@ckeditor/ckeditor5-link/src/linkimage';

ClassicEditor
	.create( document.querySelector( '#editor' ), {
		plugins: [ Image, ImageToolbar, ImageCaption, ImageStyle, ImageResize, LinkImage ],
		image: {
			toolbar: [
				'imageStyle:full',
				'imageStyle:side',
				'|',
				'imageTextAlternative',
				'|',
				'linkImage'
			]
		}
	} )
	.then( ... )
	.catch( ... );
```

<info-box info>
	Read more about {@link builds/guides/integration/installing-plugins installing plugins}.
</info-box>

## Common API

The {@link module:image/image~Image} plugin registers:

* The `'imageTextAlternative'` button.
* The {@link module:image/imagetextalternative/imagetextalternativecommand~ImageTextAlternativeCommand `'imageTextAlternative'` command}
* The {@link module:image/image/imageinsertcommand~ImageInsertCommand `'imageInsert'` command} that accepts a source (e.g. a URL) of an image to insert.

The {@link module:image/imagestyle~ImageStyle} plugin registers:

* A button for each defined style, for example: `'imageStyle:full'` and `'imageStyle:side'`.
* The {@link module:image/imagestyle/imagestylecommand~ImageStyleCommand `'imageStyle'` command} that accepts a value based on the {@link module:image/image~ImageConfig#styles `image.styles`} configuration option (for example, `'full'` and `'side'`):

	```js
	editor.execute( 'imageStyle', { value: 'side' } );
	```

The {@link module:image/imageupload~ImageUpload} plugin registers:

* The `'imageUpload'` button that opens the native file browser to let you upload a file directly from your disk.
* The {@link module:image/imageupload/imageuploadcommand~ImageUploadCommand `'imageUpload'` command} that accepts the file to upload.

The {@link module:image/imageresize~ImageResize} plugin registers:

* The {@link module:image/imageresize/imageresizecommand~ImageResizeCommand `'imageResize'` command} that accepts the target width.

<info-box>
	We recommend using the official {@link framework/guides/development-tools#ckeditor-5-inspector CKEditor 5 inspector} for development and debugging. It will give you tons of useful information about the state of the editor such as internal data structures, selection, commands, and many more.
</info-box>

## Contribute

The source code of the feature is available on GitHub in https://github.com/ckeditor/ckeditor5/tree/master/packages/ckeditor5-image.
