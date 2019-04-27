# Tensorflow_Blood_Cell_Image_Training
This is for train blood cell images using tensorflow. This technique helps us to predicts the name of the cell in an image.

#Steps
1. First we need to install ubuntu on your PC. I already explained how to install ubuntu on our PC. Do the steps 1 to 6 following this link: https://github.com/Zahid-Hasan-Jony/Python_Blood_Cell_Detection/blob/master/README.md 

2. Second we need to install tensorflow. Here we have to create vitual environment on our system. This is the best way to intall tensorflow after creating virtual environment. Because we don't need to much worry about our system if we do any mistake. Follow this video. (link: https://www.youtube.com/watch?v=FuRSeRe88sw )

**In this video they use the command pip. If you have installed python3 on your system then you will need to use pip3 command instead of pip.**

**You can install pip3 by writting commands given bellow in your terminal**

-sudo apt update

-sudo apt intall python3-pip

**check either it properly installed or not**

-pip3 --Version

It will pass like "pip 9.01 from /usr/lib/python3/dist-packages" if properly installed.

3. Training Section-
This senction is based on the following (link: https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/#0 ). Basically this link for train flower images. Here we are going to train blood cell images so it's better to ignore that link.
After activate your virtual environment following the video pass all the steps given bellow.
>Type on your terminal

-git clone https://github.com/googlecodelabs/tensorflow-for-poets-2

-Then go to the file myvenv and rename "tensorflow-for-poets-2" to "blood-cell".

-Go back to terminal and write "cd blood-cell" (ignore " ")

-curl http://download.tensorflow.org/example_images/flower_photos.tgz \
    | tar xz -C tf_files

-Then go to the file "blood-cell" folder to delete "flower_photos" folder and then paste "Extract_cells" folder to the same directory.

-Go back to terminal and write "IMAGE_SIZE=128"

-ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"

-tensorboard --logdir tf_files/training_summaries &

-pkill -f "tensorboard"

-python3 -m scripts.retrain -h

-python3 -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=tf_files/Extract_cells

-python3 -m scripts.label_image -h

**Check your input image using command**

-python3 -m scripts.label_image \
    --graph=tf_files/retrained_graph.pb  \
    --image="change with your image directory"



Let me know if you have any query!

#Myself Zahid Hasan

Gmail: zahidjony52@gmail.com
