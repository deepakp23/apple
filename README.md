# apple
ML/DL Assignment
**Steps used for the process:**

1) Created a train directory, to place all the images.
2) Preprocessing:
    a)  The images were of different channels, so used **PIL** Package to make all images to "RGB".
    b)  Resized all the images to 300, 300 and placed all the images under "Resized_image" directory.
    c)  Created another directory inside resized image named as "other".
3) Model: Used the below model
          model = keras.models.Sequential([
                                 keras.layers.Conv2D(16, (3,3), activation='relu', input_shape = (300,300,3)),
                                 keras.layers.MaxPool2D((2,2)),
                                 
                                 keras.layers.Conv2D(32 , (3,3), activation='relu'),
                                 keras.layers.MaxPool2D((2,2)),

                                 keras.layers.Conv2D(64,(3,3), activation='relu'),
                                 keras.layers.MaxPool2D(2,2),

                                 keras.layers.Conv2D(64,(3,3), activation='relu'),
                                 keras.layers.MaxPool2D(2,2),

                                 keras.layers.Conv2D(64,(3,3), activation='relu'),
                                 keras.layers.MaxPool2D(2,2),

                                 keras.layers.Flatten(),
                                 keras.layers.Dense(512, activation = 'relu'),
                                 keras.layers.Dense(1,activation='sigmoid')

            ])
 5) Model compilation:
            **Optimizer**: RMSProp
            **loss**: BinaryCrossentrpy (As we are doing binary classification)
            
6) Data Augmentation:
          As the amount of data is very less, more data is required to be generated using given images.
          **ImageDataGenerator** creates new images by flipping, tilting etc.
          
7) Prediction: 
          A test directory is created to place image, which the model will predict.
