# ANPR-Convolutional-Neural-Network
A convolutional neural network implemented using Theano for Automatic Number Plate recognition.The idea of this project is to recongnize vehicle registration number from the images of vehicles in real world. As the images are captured in raw format, The images needs to be preprocessed before feeding to the network. Following are the steps involved in this project

## Necessary Steps
- Number plate localization
- Image processing
- License plate extraction
- Character Segmentation
- Training CNN for image recongnition

## Training datasets
The project uses MNIST dataset for numbers (0 to 9) and uses similar kind of dataset for alphabets recoginition [this] (https://www.kaggle.com/sachinpatel21/az-handwritten-alphabets-in-csv-format). The data prepration steps combines both the datasets in a single dataset and split it into training and testing datasets. A Convolutional Neural Network is trained using Theano and saved the weights and biases as python's pickle file. The code can also be run on GPU which makes training process faster. The model accuracy was 99% with two convoutional pool layers. Training CNN for such a hughe dataset is very time consuming and requires a lot of CPU power, There are two ways to train CNN in cloud

- Training CNN on free Google Cloud - I will be covering this part in a YouTube Video
- Training CNN on rented GPU on cloud - Video link to be attached.


## Character Segmentation
The steps for character segmentation include vertical edge detection together with horizontal projection for upper and lower boundary removal, and image binarization together with vertical projection to find the segmenting points. After we get the number plate, The character segmentation divides the license plate into individual character images and feeds directly to reconginition algorithm, which inturn saves the output in string format.

![blur.png](https://github.com/Aarif1430/ANPR-Convolutional-Neural-Network/blob/master/Images/blur_process.png) ![contours.png](https://github.com/Aarif1430/ANPR-Convolutional-Neural-Network/blob/master/Images/contours.png) ![segmentation.png](https://github.com/Aarif1430/ANPR-Convolutional-Neural-Network/blob/master/Images/segmentation.png)

After we have got segments of image, image is divided into number of segments and sorted based on the area. There is a scope to appy other filtering methods as well to exacts find the segments of interest.

## CNN image recgnition
The invidivdual segments are feed to trained CNN for recongnition and output is saved in string format. 

## Credits 

The project was inspired by [Micheal_Nelson](http://neuralnetworksanddeeplearning.com/). The idea was to solve a real world problem using concepts described in book. [3Blue1Brown](https://www.youtube.com/watch?v=aircAruvnKk&t=7s) has also got a good playlist on neural networks for indepth understanding of backpropagation.
