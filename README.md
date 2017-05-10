# Monopoly Vectors
---
I wanted to make a custom Monopoly Community Chest card for my wife, but I could not find a usable source for the Community Chest/Chance graphics. Most were very small and pixelated. Plus, they were 72 DPI so print versions would look pretty bad.

I have created for everyone a set of Monopoly Community Chest and Chance vector (SVG) images created from GIMP.

In this repo I have included the GIMP projects, PNG versions of the GIMP projects, and 1200 DPI SVG images.

# How can I do it myself?
The process was pretty arduous but once I got it down it went pretty quickly.

* Scan each card as a 600 DPI PDF file.
* Open each PDF and enlarge it as large as my 2880x1800 Retina display could display.
* Take a screen shot of the graphic.
* Open the screen shot PNG in GIMP.
* Convert the image to Grayscale: Image > Mode > Grayscale.
* Use the Eraser tool to remove and unwanted text and blemishes.
* Click the Select By Color tool and adjust the threshold accordingly. You may have to play around with it a little bit. I found that for Community Chest cards a setting of ~80 worked well and for Chance cards a setting of ~50 worked well.
* Once the threshold is selected, click a black area of the graphic and you should see just the graphic selected. Copy the selected area to the clipboard with Edit > Copy.
* Create a new image with File > New.
* In the new file dialog expand Advanced Options and set both X resolution and Y resolution to 600 pixels per inch.
* Color space should be set to Grayscale.
* Fill with should be set to Transparency.
* Click OK to create the blank image.
* Paste the copied select into the new document with Edit > Paste.
* Convert the new image to 1 bit color: Image > Mode > Indexed...
* Check the Use black and white (1-bit) palette radio button and click Convert.
* Crop unused space around the graphic: Image > Autocrop Image.
* Color the white edges around your graphic with black. I am not sure why GIMP does this. I am not an expert.
* Set the forground color to black, select the paintbrush, and change the brush size to about 180.
* Paint the entire image with the black paintbrush.
* Save the image as something like "Community Chest - <card text>.xcf". You know have the project saved.
* Export the image as a PNG: File > Export As... Change the extension to png and GIMP will know what to do.
* I set the compression level to 0 for the highest quality. Click Export to save the file.
* To convert your PNG to an SVG file requires to steps.
  * Convert your PNG to a PNM file: convert source.png dest.pnm
  * Convert your PNM to an SVG file: potrace source.png dest.svg
* To convert your SVG to a very high quality PNG use ImageMagick's convert utility: convert -background none -depth 1 -units PixelsPerInch -density 1200 source.svg dest.png
