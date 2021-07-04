# Food-Detection-w-Machine-Learning

This is the implementation Machine Learning in the Food Detection feature of Health Inspector Application from Eunoia-Bangkit Capstone Project. Shortly we use transfer learning method with Inception V3 as the base model, and then the base model feed into our own neural network. But before we explain the steps for the MLOps, we provide the link of Android Repository, Cloud Repository, Slide Presentation, Presentation Video, and Demo Application Video.

Android : https://github.com/lukifenca/CapstoneProject
Cloud : https://github.com/melvern03/eunoia_final
Slide : https://docs.google.com/presentation/d/1x9nOH1vjMlMPFT82UvqW9i5YWj4ut1cZxMD-REFIoNw/edit?usp=sharing
Presentation : https://youtu.be/rLsUw9X5q5E
Demo : https://youtu.be/z1gU14wepFc

1. First you can find the public dataset available at Kaggle (https://www.kaggle.com/kmader/food41)
2. We do cleaning the data locally so we reduce the size of the dataset to 200 train data and 50 validation data for each class and we also only use 20 class for the sake of time efficiency. This is just prototype so after this maybe we could train it on bigger dataset.
3. For the preprocessing until export the model you can see the complete code in here https://github.com/zogojogo/Food-Detection-w-Machine-Learning/blob/main/Food_Detection_w_Food101_datasets.ipynb
4. For the preprocessing steps, we use Image Data Generator provided by Tensorflow to preprocess the image. Including data augmentation, rescale to 0-1, resize, and create the data that will be feed into the model.fit
5. Create the model using Sequential layers from Keras API and with the base model we use Inception V3 from tensorflow applications module or you can find it by yourself because that model is available online.
6. Train the model with model.fit, actually I use 25 epochs just because at that time we are running out of time. But I suggest you could use 80 epochs for the best performance.
7. We already have the model and the last step is to save it and export to tensorflow lite because we want to deploy it on Android Devices. We can see in the colab notebook that I firstly save it to the Keras format and then I store it to the google drive so I can use it again later, and then I convert it to SavedModel format or .pb format to test it on Google AI Platform. After that we can convert it to tflite format that already provided by Tensorflow.
