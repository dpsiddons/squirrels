# squirrels
An AI project to discourage squirrels
I was inspired by Jeremy Merrill's project to keep squirrels from his bird feeder by using a Raspberry Pi with a camera to detect the presence of squirrels on the feeder, and squirting them with a hose:
https://jeremybmerrill.com/blog/2022/01/squirrel-soaker-9000-repelling-squirrels-with-ai.html
I didn't want to involve any remote analysis (colab, aws, which Jeremy used) so I used a different approach to building the model. I also made a custom telephoto lens for the Pi camera to give a closer view of the feeder in the hope it would make for a better model.
I used TensorFlow to build the model locally on my workstation. It is a Keras sequential model, and follows this example:
https://www.tensorflow.org/tutorials/load_data/images 
and then converted it to Tflite for running on the Pi. I had some difficulty using the tflite model since the basic converter did not add signatures to the model, which tflite needs. I found this link which wraps the model with the signature info:
https://maeglin89273.medium.com/convert-savedmodel-to-tflite-model-with-signaturedef-debee6955cb7  
I used Jeremy's code to sequence things and to populate a web page with results.
I first collected samples by taking pictures every minute during the times I knew the squirrels were most active (mornings and late afternoon) using a couple of crontab entries which called a shell script to take and store a picture. I then sorted these images into "yes" and "no" directories using a simple Octave script to show the images sequentially, and move them into the right directory based on a keypress.
[work in progress]
