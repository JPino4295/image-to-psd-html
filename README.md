# Image to PSD Separator

A lightweight, strictly client-side HTML/JavaScript tool that converts flat grayscale images into layered Photoshop Document (.psd) files. It automatically extracts black lineart onto a transparent layer and provides a solid white background layer, making the file instantly ready for coloring in Photopea, Photoshop, or GIMP.

## Features

* **Automated Lineart Extraction:** Calculates pixel luminance to convert white backgrounds into transparency while preserving the opacity of darker lines.
* **Ready-to-Paint Layers:** Generates a PSD with a dedicated `Lineart` layer on top and a solid white `Background` layer underneath.
* **100% Local Processing:** All image processing and PSD generation happens directly in your web browser. No files are uploaded to external servers.
* **Zero Installation:** Runs entirely from a single `.html` file.

## Prerequisites

* A modern web browser (Chrome, Firefox, Safari, Edge, etc.).
* An active internet connection (strictly for fetching the lightweight `ag-psd` library from its CDN).

## Usage

1. Save the provided code as an HTML file (e.g., `image_to_psd.html`).
2. Double-click the file to open it in your web browser.
3. Click the file upload button on the page.
4. Select your flat grayscale lineart image from your computer.
5. The script will process the pixels and automatically download a file named `extracted_lineart.psd`.
6. Open the downloaded `.psd` file in your preferred image editor to begin editing.

## Technical Details

* **HTML5 Canvas API:** Used for reading the image data, iterating through the RGBA array, and calculating luminance (`0.299*R + 0.587*G + 0.114*B`) to manipulate the alpha channel.
* **ag-psd:** An open-source JavaScript library loaded via CDN, used here to construct the binary `.psd` document hierarchy (canvas references, layer names, dimensions) and encode the final buffer for download.
