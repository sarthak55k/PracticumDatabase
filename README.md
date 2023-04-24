# Assignment 6

### Design

#### Overview

Our design for Image Manipulation and Enhancement utilizes the Model-View-Controller architecture.
The combination of the classes ImageProcessorImpl and its extended child class MoreImageProcessorImpl and EvenMoreImageProcessorImpl 
are the model. The class ROModelImpl is alos part of model that view can gets data by calling the methods in ROModelImpl. 
The class, ImageProcessorControllerImpl, and its extended child class MoreImageProcessorControllerImpl
are controllers which connect to the model. ImageProcessorControllerGUIImpl is also a controller that gets user inputs from viewer and pass 
command to model and then passes the result to the viewer. Command Design Pattern is used to deal with multiple commands from the user and 
then pass the commands to the model. The class GUIViewImpl is the viewer that constructs a Graphical User Interface. 
MainProgram is used to run the whole program.

#### Model(Complete & Updated)

$\color{red}Previous$

ImageProcessorImpl is the model which implements ImageProcessor. It consists of the methods to process the images.
The hashmap stores the result of the processed 3D image array and its corresponding id. Another hashmap is created to store the 
image's max value and its corresponding id. To accommodate more methods that process images and more image types, 
the MoreImageProcessor interface is created and extended from ImageProcessor. MoreImageProcessorImpl 
class extends from ImageProcessorImpl and implements the MoreImageProcessor interface. Like the parent class ImageProcessorImpl, 
the processed 3D image array and max value, and its corresponding id are stored in the hashmap. 

$\color{red}Updated$

ROModelImpl that implements ROModel is created. ROModel is a read-only model. The introduction of ROModel is to ensure that 
the viewer can have access to the data, but cannot modify the data. Also, instead of getting data from controller, we can get data by calling
methods in ROModel. The data flow to display/update image and histogram will be viewer -> ROModel -> Viewer instead of Viewer -> Controller 
-> Model -> Controller -> Viewer. Also, with the introduction of ROModel, ImageProcessor interface extends ROModel interface. 
Since ImageProcessorImpl implements ImageProcessor, the newly added methods in ROModel interface will be implemented in ImageProcessorImpl class.

$\color{red}New$

To create a histogram for an image, the class EvenMoreImageProcessorImpl is created. This class extends MoreImageProcessorImpl and implements the EvenMoreImageProcessor interface. A hashmap is created to store all images' histograms. Each image's frequency of each pixel value for each channel 
and frequency of intensity value will be stored in the hashmap.


#### Controller(Complete & Updated)

The command design pattern is used to deal with multiple commands. The usage of this design pattern makes the design more extensible. 

$\color{red}Previous$

ImageProcessorControllerImpl that implements ImageProcessorController is the controller. The Command design pattern makes the design more extensible. ImageProcessorCommand interface is created. For each command, a class is created and implements the ImageProcessorCommand interface. Within the class, a constructor is created to ensure that length of the command is correct and a method is used to pass the command to the model. All commands are stored in a hashmap with the command as the key and its corresponding function and input string as value. Besides the utilization of the command design pattern, the read and write image file methods are in controller side to ensure that controllers get the user inputs, store the data into the model or get data from the model and output the results to the user. An abstract class is created to have a load and save method to extend. Both load and save methods contain the same method for checking image extension.

MoreImageProcessorControllerImpl extends ImageProcessorController class is created to work with MoreImageProcessorImpl class. 
Also, the MoreImageProcessorCommand interface is created. For all new commands, a class is created and implements the MoreImageProcessorCommand 
interface which follows the command design pattern. All new commands are stored in a hashmap with the command as a string and its 
corresponding function and input string as value.

$\color{red}New$

ImageProcessorControllerGUIImpl class implements Features interface. This class is used to work with a GUI-based view. This class provides a view of all 
callbacks. It gets a command from the viewer and passes the command to the command class. The command class can then passes data to the model and after the model processes the data, it will pass the result to the controller and have controller to ask view to show the result. 

#### Viewer(Complete & Updated)

$\color{red}Previous$

The OutPutStream is used to receive all the inputs from the user and catch the exception and print it out to the user. Users can know
whether their commands are successfully run or failed to run. They can also get the reason behind the unsuccessful command input. 

$\color{red}New$

Besides the view from the command prompt, a GUI-based view is designed. The view consists of panels to show a list of image names, show an image, 
show an image's histogram, and a batch of buttons to do operations on an image. The view takes in a ROModel and gets data by calling the 
methods in ROModel. The view can also prompt different dialogues by clicking different buttons. It will display the image and its histogram if the 
operation succeeds. Otherwise, a message will be prompted and the user can know what is wrong with his/her operation.

#### MainProgram(Complete & Updated)

$\color{red}Previous$

The main method in MainProgram class runs the whole program. It creates a new model and passes the model to the controller. The controller 
receives inputs and gives outputs. When the controller is executed, the user can type in a command or type in a txt file. 
The controller receives that input and transfers the input to the model, the model can run a specific function in the 
EvenMoreImageProcessorImpl class and then stores the processed 3D image array and its corresponding id in hashmap. 
For each input, the user receives a message that can either be a successful one or a failed one.

$\color{red}New$

Besides getting a txt file and asking the user to type in a command, the program prompts a GUI-based view. Within the viewer, the user can do operations by clicking the image name and buttons. After the user click the button, a dialogue will pop up. The user can enter image id, select folder to load image,
select an item in a dropdown list, etc. After all the information is entered, the user can click the last button to have the information as a string to pass to the methods in ImageProcessorControllerGUIImpl class. The method in ImageProcessorControllerGUIImpl class can then pass the command to the command 
class to have it execute. If the execution is successful, the controller can have viewer to set image and its histogram. The viewer can get an image and its histogram through ROModel and have them shown on the screen. Otherwise, a message dialogue will be prompted to tell the user about what is wrong with his/her operation.

### Ways to run program

```
A. Run a JAR file
```
a. pass in a txt file and then quit

1. Open terminal and locate to the folder "res" which contains the JAR file.
2. Type "java -jar Assignment6.jar -file example-script-forjarfile.txt" as a command line argument and hit enter.
3. The script will be run and prompt successful messages. After all commands inside scripts are run, the system will quit.

b. type in a command 

1. Open terminal and locate to the folder "res" which contains the JAR file.
2. Type "java -jar Assignment6.jar -text" as a command line argument and hit enter.
3. The command will be run and prompt successful messages. 

c. start a GUI-based View

1. Open terminal and locate to the folder "res" which contains the JAR file.
2. Type "java -jar Assignment6.jar" as a command line argument and hit enter.
3. A GUI-based view will be started. User can click buttons to do operations on images. 

```
B. Run main method in MainProgram class
```

1. Run the program "Run: MainProgram.main()".
2. A GUI-based view will appear. You can click buttons to do operations on images.

### Citation for the source of images

The image, feep.ppm, is downloaded from the
website https://people.sc.fsu.edu/~jburkardt/data/ppma/ppma.html. All the other ppm images inside
test/testImage folder are created by Yangjiawen Xu for test purposes.

The image, fall.ppm is taken by Yangjiawen Xu, who authorizes the usage for this project.
