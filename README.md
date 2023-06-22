# squirrels
An AI project to discourage squirrels
I was inspired by Jeremy Merrill's project to keep squirrels from his bird feeder by using a Raspberry Pi with a camera to detect the presence of squirrels on the feeder, and squirting them with a hose:
https://jeremybmerrill.com/blog/2022/01/squirrel-soaker-9000-repelling-squirrels-with-ai.html
I didn't want to involve any remote analysis (colab, aws, which Jeremy used) so I used a different approach to building the model. I also made a custom telephoto lens for the Pi camera to give a closer view of the feeder in the hope it would make for a better model.
I used TensorFlow to build the model on my workstation, and then converted it to Tflite for running on the Pi. I used Jeremy's code to sequence things and to populate a web page with results.
