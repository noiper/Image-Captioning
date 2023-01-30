# Image-Captioning

This is a model to generate caption for images. The dataset can be found here: https://forms.illinois.edu/sec/1713398, which contains 8000 image caption pairs. I split the samples into training, validation, test with a ratio of 6:1:1.

## Methods

Here is the overall architecture of the model.

![model architecture](https://github.com/noiper/Image-Captioning/blob/main/src/architecture.png)

Given a certain image, the model first uses an encoder to map the image to a lower dimension vector. Then the vector is added to the input of the LSTM model to generate the text. The image encoder used is based on Inception V3, and the last layer is removed to get the embedding. The generator model uses a bi-LSTM and a softmax layer to get the prediction. The caption starts with a \<start\> token. As long as the predicted token is not \<end\> or the sequence reaches its maximum length, the predicted token is added to the previous input and make another prediction. In the end, we have our predicted caption.

## Results

Now, let's see our model performance!
Here is one example of captions for the training images, which is pretty reasonable.

![model architecture](https://github.com/noiper/Image-Captioning/blob/main/src/example1.png)

Caption: A dog and a dog are in the snow.

Here is one example of captions for the development images. Although not good as the training image, it still makes much sense.

![model architecture](https://github.com/noiper/Image-Captioning/blob/main/src/example2.png)

Caption: 'A man in a blue shirt and a woman in a white shirt.
