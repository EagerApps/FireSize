# FireSize + Javascript

This project uses the fantastic [FireSize](http://firesize.com/) to automatically optimize images
on an existing website.  This is a community project, not affiliated with the FireSize team.

![Timeline](https://i.imgur.com/GCwIj4n.png)

The upper timeline is optimized with FireSize, the lower is not.

## Usage

Add `optimize.js` to the **`<head>`** of your site.  Done!

## How It Works

We use a [MutationObserver](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)
to detect when `<img>` elements are parsed by the browser, and update the `src`
to an optimized version before the browser begins to download the original image.

If the image loading errors for any reason, the image will automatically be reverted to it's
original src.

It wouldn't be possible without the flexability of the [FireSize project](http://firesize.com/).

### Optimizations

We shrink the size of the image if we are able to determine at least one of the dimentions.
To do this, the element must have a defined height or width (either as an attribute or in CSS).

If we don't have size information, we still will optimize the image to use the FireSize CDN,
which can have a significant performance improvement.

### Options

If you don't wish for a specific image to be optimized, add the `no-firesize` class to it.

### Cavets

- Doesn't optimize images inserted by JavaScript dynamically.

## Errata

This project is released under the MIT license.

We aren't affiliated with [FireSize](http://firesize).

Please contribute by opening an Issue or Pull Request.
