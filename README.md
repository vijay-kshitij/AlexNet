# AlexNet
## This is part of my coursework Machine Learning (CSE 574).

We have been provided with cnn_dataset, this dataset has 10000 images for each classes which are food, vehicles & dogs as shown below:
![Screenshot 2023-10-19 at 2 34 11 AM](https://github.com/vijay-kshitij/AlexNet/assets/51355853/9a36746b-4b0d-421c-9dd0-14a8cb46b0fe)

Here 0 belongs to Dogs, 1 to Vehicles & 2 to Food class.
Since we are provided just with images of separate classes, so we created a csv file, which has enabled us to manage the data more accurately. 
After that we used OpenCV for visualizing images for different classes by changing the RGB channels . It is shown as below:
![Screenshot 2023-10-19 at 2 35 56 AM](https://github.com/vijay-kshitij/AlexNet/assets/51355853/f493fe4d-464b-4ff6-92a9-ca966aaa9b33) 
![Screenshot 2023-10-19 at 2 36 19 AM](https://github.com/vijay-kshitij/AlexNet/assets/51355853/da0d4c79-455d-4d96-a7b3-a68b7b92d860)
![Screenshot 2023-10-19 at 2 36 33 AM](https://github.com/vijay-kshitij/AlexNet/assets/51355853/25eeeedd-e527-45c4-b78b-4cbe9cca9d6f)

As visible from the above the images are of varying size thus there is need to scale these images hence we readtheimagesandscaleditto224*224*3. Also,theinputsizeforAlexnetis224*224*3hencere-scaling makes more sense.
After that we split the dataset into testing and training, we did not split into validation as we wanted our model to learn more on the training dataset (considering the blurriness of the images in the dataset). Hence, we trained our model on 29000 images, tested it on 1000 image s.
Now considering the Alexnet architecture:
We used convolution layer, maxpooling layers to build the network. Additionally we used batchnormalisation which is a technique helps in enhancing the performance of the neural networks, this optimization enhanced the model performance. Also, since we re -scaled the images to (224,224) we could use valid padding, which essentially means no padding. We tested with various optimizer but at the end wefoundAdamoptimizertobethebestoptimizerhenceweusedit. Also,theoutputlayerofAlexnet produce one-hot encoding of the labels hence it is of (None,3) dimension.
After compiling the Alexnet, we trained it on our training dataset, we wrote the custom fit method for neural network training, we experimented with epochs ranging from 20 to 50 but we found the most optimal to be 40. It took the model 2 hours with GPU to train on the training dataset.
