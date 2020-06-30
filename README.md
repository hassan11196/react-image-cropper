## React Image Cropper
🚨🚨 Abandoned. The Size of cropped image was unusually large. I couldnt find the issue and moved to 
[react-avatar-editor](https://www.npmjs.com/package/react-avatar-editor)

### This is a fork with fixes for Custom Code for cropping limits.

### Merged Changes from tinsaye and slidewiki.

[![Downloads](https://img.shields.io/npm/dt/react-image-cropper.svg)](https://www.npmjs.com/package/react-image-cropper)
[![Version](https://img.shields.io/npm/v/react-image-cropper.svg)](https://www.npmjs.com/package/react-image-cropper)

This project has been forked from [https://github.com/jerryshew/react-image-cropper](https://github.com/jerryshew/react-image-cropper), v1.1.2 and includes some changes that jerryshew did not wanted to merge. See this repo also for React versions >0.15.

[![Downloads](https://img.shields.io/npm/dt/slidewiki-react-image-cropper.svg)](https://www.npmjs.com/package/slidewiki-react-image-cropper)
[![Version](https://img.shields.io/npm/v/slidewiki-react-image-cropper.svg)](https://www.npmjs.com/package/slidewiki-react-image-cropper)

See the original repository for a demo of the image cropper - [https://github.com/jerryshew/react-image-cropper](https://github.com/jerryshew/react-image-cropper)

**Our custom changes Custom:**

+ limit the cropper container height to a max value (useful for portait images (e.g. 9:21), that would cause the cropper to stretch a lot)
+ define max crop sizes that cause the cropper to limit the resulting image to some maximum values

### How to Use

+ `import {Cropper} from 'react-image-cropper'`

+ styles are all inline

+ define Cropper with src, and ref to execute crop method  

```
<Cropper src="http://braavos.me/images/posts/college-rock/the-smiths.png" ref="cropper"/>
```

+ crop and get image url

`image.src = this.refs.cropper.crop()`

+ get crop values

OPTIONS (optional):

+ maxHeight : make sure the cropped image is not bigger than this max height
+ maxWidth : make sure the cropped image is not bigger than this max width

`image.src = this.refs.cropper.crop(maxWidth, maxHeight)`

`var values = this.refs.cropper.values()`

+ onChange for preview

(values) => onChange(values)

+ custom use

| prop  |  value   |
|:-------:|:--------|
| ratio | width / height |
| width | cropper frame width |
| height | cropper frame height |
| originX | cropper original position(x axis), accroding to image left|
| originY | cropper original position(Y axis), accroding to image top|
| fixedRatio | turn on/off fixed ratio (bool default true) |
| allowNewSelection | allow user to create a new selection instead of reusing initial selection (bool default true) |
| styles | specify styles to override inline styles |
| onImgLoad | specify fuction callback to run when the image completed loading |
| beforeImgload | specify function callback to run when the image size value is ready but image is not completed loading |
| onChange | triggred when dragging stop, get values of cropper |
| limitHeight | limit the height of the cropper, e.g. if the img is a portrait |
