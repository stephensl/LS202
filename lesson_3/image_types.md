# Image Types

Most commonly used are `jpg`, `png`, and `gif`

#

## JPG

Most common image format used in web documents. 

  - Provide balance of image quality and compression
  - Compression
    - encodes file to reduce size
    - "lossy" form of compression 
      - lose information in exchange for size reduction
      - sacrifices quality for compression
    - can set amount of compression and associates "lossiness" when save jpg file. 
  
  *may require experimentation to find right balance*

#

## PNG

Generally, jpgs do not work well as CSS background images
- png often best choice for backgrounds/non-photographic images.

- Compression
  - non-lossy
  - larger file sizes in some cases

- Features
  - single-color and alpha transparency
    - allows to see background behind image while still viewing image's main subject. 
      - useful with logos, icons, line drawings
  - Single Color Transparency
    - allows part of an image to be entirely clear by reserving a single color -any pixel that matches that color in the png reveals the content (usually a background color) behind the image.
  - Alpha Transparency
    - adds an alpha channel to images
      - allows up to 65,536 different levels of transparency tinted by color

*pngs are ideal for images that need all their detail, transparency, or that must support more than 16.7 million colors.* 

#

## GIF

Suitable for small images used as user-interface icons in an application. 
- limited color range (256 colors)
- tiny file sizes

*useful when size, detail, and broad color palette are not significant.* 

#


