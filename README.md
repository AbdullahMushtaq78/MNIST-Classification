# MNIST Handwritten Digits Classification<br/>
## MNIST is one of the most used datasets to classify digits into different classes (0 to 9).<br/>
- This dataset contains 60,000 images of 28x28 size. These are all the images of handwritten digits.
- Along with images, the labels are also given.
- Neural Networks are used in Supervised Learning, which is why labels play an important role in learning models.
Model:
- First, the image data is normalized by dividing each pixel value by 255. The images are in black and white, and the only value that each pixel can take is between 0-255.
- After normalization, the images are converted into the 1D array to flatten the data so it can be passed to the model.
- And then, data is split into two groups Training Dataset & Testing Dataset (for model evaluation). <br/><br/>
  - Learning Model Initialization:
    - As neural networks consist of different layers of units, In this model, a total of 4 layers are used to build a model.
    - First Layer consists of 784 neurons equal to the input size of each image after flattening the image array with the activation function as 'relu.'
    - The second layer consists of 256 neurons with 'relu' as an activation function.
    - Third Layer consists of 128 neurons with 'relu' as an activation function.
    - The fourth layer consists of 10 neurons because our dataset has only ten types of Digits. Used 'softmax' as an activation function as softmax is the most efficient and mostly used activation function for multi-class classification problems.
    ```
    model = Sequential([
       Dense(units = 784, input_shape = (784,), activation = 'relu'),
       Dense(units = 256, activation = 'relu'),
       Dense(units = 128, activation = 'relu'),
       Dense(units = 10, activation = 'softmax')])
    ```
    <br/>
  - Optimizer:
    - Adam optimizer ```tf.keras.optimizers.Adam()``` is used as an optimizer in this project because it is one of the best optimizers for learning algorithms.
  - Loss Function:
    - For multi-class classification, ```'sparse_categorical_crossentropy'``` is used. 
  - Training Results:
    - After training, the accuracy of the model is: ```96.92%``` 
  - Testing Results:
    - After testing on a separate group of images, the accuracy of the model is: ```96.439%```
  - Confusion Matrix/ Heat Map:
    - ![image](https://user-images.githubusercontent.com/96788451/194772492-f199a344-1804-4433-b1d2-f3052c71d757.png)
