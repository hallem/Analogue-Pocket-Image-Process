# Analogue Pocket Framework Image Processor

Simple image processing for APF platform and author icon images.

## Creation

The creation script converts a 521x165 platform image or a 36x356 author icon PNG image into a 16 bit greyscale bitmap, where the upper byte stores the brightness of the pixel, where white is `0x00` and black is `0xFF`. At the moment, the lower byte is always `0x00`. This image is stored rotated 90 degrees counter-clockwise (creating a resolution of 165x521).

_To prepare a platform image for display on the Pocket:_

1. Create a 521x165 greyscale platform image (transparent pixels will be converted into white)
2. Save image as PNG
3. Run:

```bash
npm run create input.png <platform_id>.bin
```

4. Place this image in the appropriate platform folder in `/Platforms/_images/`.

_To prepare an author icon image for display on the Pocket:_

1. Create a 36x36 greyscale author icon image (transparent pixels will be converted into white)
2. Save image as PNG
3. Run:

```bash
npm run create input.png icon.bin
```

4. Place this image in the appropriate core folder in the `Cores/<core_name>/`.

## Extraction

Extracting an existing platform image will invert the color (back to what it started as) and revert the 90 degree rotation performed during creation.

To extract a previously created APF platform image, run:

```bash
npm run extract platform input.bin output.png
```

To extract a previously created APF author icon image, run:

```bash
npm run extract icon input.bin output.png
```

## Links & Samples

[See the Analogue docs for more information](https://www.analogue.co/developer/docs/packaging-a-core#graphical-asset-formats)

![Analogue platform image demo](https://images.analogue.co/platform_art.2ad219560f99a334bf59ef9641c433f6.png?auto=format&w=1200&q=100&s=74e9636d11c828a74b67f9a060a59abb)

![Analogue author image demo](https://images.analogue.co/placement.84555c22c604817cde1f8c92fcdfef47.png?auto=format&w=1200&q=100&s=65d1acfc0092d8f0b476fb55f6e4d31b)