# Digital Collections Image Tools

Libraries, museums and other organizations do digitization projects to make visual material available on the web. This repository is a placeholder for scripts to process and manage the images for those projects. 

The first script here uses computer vision to automatically crop color bars and rulers from high resolution scans. 

## Quickstart

First, start the OpenCV component in a Docker container:

```
docker build -t crop https://github.com/johnjung/digital_collections_image_tools.git
docker run --rm -it -p 5000:5000 crop start
```

Then run the cropping script itself in a separate window:

```console
$ sh crop.sh

.----. .----. .----. .----.  
| {}  }| {}  }| {_  { {__    
| .--' | .-. \| {__ .-._} }  
`-'    `-' `-'`----'`----'   
 .---. .----.  .----. .----. 
/  ___}| {}  }/  {}  \| {}  }
\     }| .-. \\      /| .--' 
 `---' `-' `-' `----' `-'    

Welcome to the preservation cropping script.

Enter input directory, e.g. /Volumes/pres/EWM/ewm-0054/Masters: 
```

The following script tests cropping settings on a specific image:

```console
$ sh test.sh <red> <green> <blue> <variation> <inputfile> <outputfile>
```

In testing mode the script draws a rectangle around the image area that 
will be left after cropping- here's a sample image-

![sample image](./test_image.jpg)

And here is the sample image with cropping coordinates-

![sample image with bounding box](./test_image_show_cropping_rectangle.jpg)

## POST parameters

### image
An image containing a ruler along one edge.
that has been reduced in size.)

### red
In an rgb pixel describing the ruler's color, the red channel amount from
0-255.

### green
In an rgb pixel describing the ruler's color, the green channel amount from
0-255.

### blue
In an rgb pixel describing the ruler's color, the blue channel amount from
0-255.

### grayvariation
Fuzziness for color matching. If rgb values are 120 and grayvariation is set to
20, the script will search for objects between 100/100/100 and 140/140/140. 

## Contributing

Please contact the author with pull requests, bug reports, and feature
requests.

## Author

John Jung
