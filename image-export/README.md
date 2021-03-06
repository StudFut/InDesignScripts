# image-export.jsx

A script for Adobe InDesign to export images to web-friendly formats.

##  Installation

1. open InDesign Scripts panel
2. right-click on folder entitled "User" and select "Reveal in Explorer/Finder"
3. copy image-export.jsx to this folder

## Requirements

* image-export.jsx needs at least Adobe InDesign Version 8.0 (CS6)
* image-export_pre-cs6.jsx works with Adobe InDesign Version 7.0 (CS5) but supports only JPG output. I've tested it on CS5 but it may work on CS4 as well.

## Features

* adjusted size, bleed, transparency and orientation settings are applied and automatically exported (please note that this works not with locked layers)
* for multiple linked images, every instance is stored as separate image with a unique name and its settings
* select output directory, compression ratio, density and choose between JPG and PNG format
* support InDesign object export options
* set resolution limit

### Localization


Set interface language by changing `lang.pre` to one of the following values

* `0` English
* `1` German

For example, setting `lang.pre` to `1` will change the interface language to german.

```javascript
lang = {
  pre: 0
}
```

## Limitations

* Embedded images are not exported. Consider to convert embedded images to linked images instead.

## IDML

* for multiple instances of one image, each instance is exported with a unique filename
* the new filename is stored in the IDML as ``Label`` of the ``Rectangle`` element

```xml
<Rectangle>
  <Properties>
    <Label>
      <KeyValuePair Key="letex:fileName" Value="new-filename-a3.jpg" />
    </Label>
  </Properties>
  <!-- (...) -->
</Rectangle>
```
