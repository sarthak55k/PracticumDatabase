## List of Commands

```
A. load image-path image-name
```

Load an image from the specified path and refer it to henceforth in the program by the given image
name. "load" command should be typed before image-path and image-name. "load" command can be typed 
in upper case or lower case or mixed with upper and lower case. image-path should be typed before image-name.

For example: "load /res/fall.ppm fall" A file named "images/fall.ppm" will be loaded and save
it to the program with the given image name(fall).

```
B. save image-path image-name
```

Save the image with the given name to the specified path which should include the name of the file.
"save" command should be typed before image-path and image-name. "save" command can be typed 
in upper case or lower case or mixed with upper and lower case. image-path should be typed
before image-name.

For example: "save output/fall.ppm fall" Save the given image name to the given path.

```
C. horizontal-flip image-name dest-image-name
```

Flip an image horizontally to create a new image, referred to henceforth by the given destination
name. "horizontal-flip" command should be typed before image-name and dest-image-name. "horizontal-flip" 
command can be typed in upper case or lower case or mixed with upper and lower case. image-name 
should be typed before dest-image-name.

For example: "horizontal-flip fall-vertical fall-vertical-horizontal" Flip the given image-name
(fall-vertical) and save it to dest-image-name(fall-vertical-horizontal).

```
D. vertical-flip image-name dest-image-name
```

Flip an image vertically to create a new image, referred to henceforth by the given destination
name. "horizontal-flip" command should be typed before image-name and dest-image-name. "vertical-flip" 
command can be typed in upper case or lower case or mixed with upper and lower case. image-name 
should be typed before dest-image-name.

For example: "vertical-flip fall fall-vertical" Flip the given image-name (fall) and save it to 
dest-image-name(fall-vertical).

```
E. greyscale red-component/green-component/blue-component/value-component/intensity-component/luma-component image-name dest-image-name
```

Create a greyscale image with red component or green component or blue component or value component
or intensity component or luma component of the image with the given name and save it to the 
given dest-image-name. "greyscale" command should be typed before component name, image-name and dest-image-name.
"greyscale" command can be typed in upper case or lower case or mixed with upper and lower case. 
Component name should be typed before image-name and dest-image-name. image-name should be typed before dest-image-name.

For example: "greyscale value-component fall fall-greyscale" Create a greyscale image of image-name (fall)
with the value component and save it to dest-image-name(fall-greyscale).

```
F. brighten increment image-name dest-image-name
```

Brighten/darken the image by the given increment to create a new image. "brighten" command should be 
typed before increment, image-name and dest-image-name.
"brighten" command can be typed in upper case or lower case or mixed with upper and lower case. 
Increment should be typed before image-name and dest-image-name. image-name should be typed before dest-image-name.

For example: "brighten 10 fall fall-brighter" Brighten the image-name (fall) by 10 and save it to dest-image-name (fall-brighter)

"brighten -10 fall fall-darker" Darken the image-name (fall) by 10 and save it to dest-image-name (fall-darker)

```
G. rgb-split image-name dest-image-name-red dest-image-name-green dest-image-name-blue
```

Split the given image into three greyscale images containing its red, green and blue components respectively. 
"rgb-split" command should be typed before image-name, dest-image-name-red, dest-image-name-green and dest-image-name-blue.
"rgb-split" command can be typed in upper case or lower case or mixed with upper and lower case. 
image-name should be typed before dest-image-name-red, dest-image-name-green and dest-image-name-blue. 

For example: "rgb-split fall fall-red fall-green fall-blue" Split the given image-name(fall) into
three greyscale images dest-image-name-red(fall-red), dest-image-name-green(fall-green), 
and dest-image-name-blue(fall-blue).

```
H. rgb-combine image-name red-image green-image blue-image
```

Combine the three greyscale images into one image that gets its red, green and blue components from
the three images respectively. "rgb-combine" command should be typed before image-name, 
red-image, green-image and blue-image. "rgb-combine" command can be typed in upper case or lower case 
or mixed with upper and lower case. image-name should be typed before red-image, green-image and blue-image. 

For example: "rgb-combine fall-red-tint fall-red fall-green fall-blue" Combine red-image(fall-red), 
green-image(fall-green), and blue-image(fall-blue) and then save it into image-name(fall-red-tint).

```
I. run filePath
```

Run the txt file. "run" command should be typed before filePath. "run" command can be typed in upper case or 
lower case or mixed with upper and lower case. "run" command should be typed before filePath.

For example: "run /example-script.txt" Load file and run commands from the specified file path.

```
J. quit/q
```
Quit the program.

### More commands
```
K. blur image-name dest-image-name
```
Blur the image-name to create a new image, referred to henceforth by the given destination
name. "blur" command should be typed before image-name and dest-image-name. "blur" command 
can be typed in upper case or lower case or mixed with upper and lower case. 
image-name should be typed before dest-image-name.

For example: "blur fall fall-blur" Blur the image(fall) and then save into image-name(fall-blur).

```
L. sharpen image-name dest-image-name
```

Sharpen the image-name to create a new image, referred to henceforth by the given destination
name. "sharpen" command should be typed before image-name and dest-image-name. "sharpen" command 
can be typed in upper case or lower case or mixed with upper and lower case. 
image-name should be typed before dest-image-name.

For example: "sharpen fall fall-sharpen" Sharpen the image(fall) and then save into image-name(fall-sharpen).

```
M. greyscale image-name dest-image-name
```
Greyscale the image-name to create a new image, referred to henceforth by the given destination
name. "greyscale" command should be typed before image-name and dest-image-name. "greyscale" command 
can be typed in upper case or lower case or mixed with upper and lower case. 
image-name should be typed before dest-image-name.

For example: "greyscale fall fall-greyscale" Greyscale the image(fall) and then save into image-name(fall-greyscale).

```
N. sepia image-name dest-image-name
```
Sepia the image-name to create a new image, referred to henceforth by the given destination
name. "sepia" command should be typed before image-name and dest-image-name. "sepia" command 
can be typed in upper case or lower case or mixed with upper and lower case. 
image-name should be typed before dest-image-name.

For example: "sepia fall fall-sepia" Sepia tone the image(fall) and then save into image-name(fall-sepia).

```
O. dither image-name dest-image-name
```
Dither the image-name to create a new image, referred to henceforth by the given destination
name. "dither" command should be typed before image-name and dest-image-name. "dither" command 
can be typed in upper case or lower case or mixed with upper and lower case. 
image-name should be typed before dest-image-name.

For example: "dither fall fall-dither" Dither the image(fall) and then save into image-name(fall-dither).


## Instructions to use Graphical User Interface

When you run the MainMethod or jar file, a GUI will appear. The user interfaces includes 2 sections. 

The first section includes three sections. The frist column is your entered image names. The second column is currect image. The third column is its histogram. 

The second section is a batch of buttons. The usage of those buttons will be illustrated below.

```
A. "Load" Button
```
After clicking "Load" button, a dialogue appears with a field to enter an image id, a button "select an image" and a button "Load Image". 
By clicking the "select an image" button, user can choose a valid image file to load. After you click "Open", an image file will appear on the dialogue.
Afterwards, you click "Load Image" to load this image. You will see your entered image name on the first column. The second column is the loaded image. The third column is the loaded image's histogram.

```
B. "Save" Button
```
After clicking "Save" button, a dialogue appears with a button "Select folder and enter name to save" and a button "Save image".  
By clicking the "select folder and enter name to save" button, user can choose folder to put the image and type in an image name with a valid image extension. After you click "Save Image", an image will be saved. You will see a dialogue that shows "Save Image Succeeds" and can browse folder to 
see your saved image.

```
C. "Brighten/Darken" Button
```
After clicking "Brighten/Darken" button, a dialogue appears with a field to enter a positive/negative integer, a field to enter an image id and 
a button "Brighten/Darken". After entering the value and image name, user can click the button to get a brightened/darkened image.
Your entered image name will appear on the first column. The second column is the brightened/darkened image. The third column is the 
brightened/darkened image's histogram.

```
C. "Flip" Button
```
After clicking "Flip" button, a dialogue appears with a dragdown list to select direction, a field to enter an image id and 
a button "Flip".  After selecting the direction and entering image name, user can click the button to get a flipped image.
Your entered image name will appear on the first column. The second column is the flipped image. The third column is 
the flipped image's histogram.

```
D. "Visualize Component" Button
```
After clicking "Visualize Component" button, a dialogue appears with a dragdown list to select a component, a field to enter an image id and 
a button "Visualize Component".  After selecting the component and entering image name, user can click the button to get a visualized image of a component. Your entered image name will appear on the first column. The second column is the visualized-component image. The third column is the visualized-component image's histogram.

```
E. "Split" Button
```
After clicking "Split" button, a dialogue appears with three fields to enter image ids and a button "Split". After entering image names, 
user can click the button to get three split images. Your entered image names will appear on the first column. 
The second column is the one of splitted images. The third column is the splitted image's histogram.

```
F. "Combine" Button 
```
After clicking "Combine" button, a dialogue appears with three dragdown lists to select an image name, a textfield to enter an image name 
and a button "Combine". After selecting images and entering an image name, user can click the button to get a combined image. 
Your entered image name will appear on the first column. The second column is the combined images. The third column is the 
combined image's histogram.

```
F. "Filter" Button 
```
After clicking "Filter" button, a dialogue appears with a dragdown lists to select a kernel, a textfield to enter an image name 
and a button "Filter". After selecting a kernel and entering an image name, user can get a filtered image. Your entered image name 
will appear on the first column. The second column is the filtered image. The third column is the filtered image's histogram.

```
F. "Sepia" Button 
```
After clicking "Sepia" button, a dialogue appears with a textfield to enter an image name and a button "Sepia".  
After entering the image name, user can click the button to get a sepia toned image. Your entered image name will appear on the 
first column. The second column is the sepia toned image. The third column is the sepia toned image's histogram.

```
G. "Greyscale" Button 
```
After clicking "Greyscale" button, a dialogue appears with a textfield to enter an image name and a button "Greyscale".  
After entering the image name, user can click the button to get a a greyscaled image. Your entered image name will appear on the 
first column. The second column is the grayscaled image. The third column is the grayscaled image's histogram.

```
H. "Dither" Button 
```
After clicking "Dither" button, a dialogue appears with a textfield to enter an image name and a button "Dither".  
After entering the image name, user can click the button to get a dithered image. Your entered image name will appear on the 
first column. The second column is the dithered image. The third column is the dithered image's histogram.



