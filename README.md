# Transfer-Learning---VGGNET

Performed 3 types of model using VGGNET by Transfer learning.

//
### Model 1 

1. Used VGG-16 pretrained network without Fully Connected layers and initilized all the weights with Imagenet trained weights. 
2. After VGG-16 network without FC layers, add a new Conv block ( 1 Conv layer and 1 Maxpooling ), 2 FC layers and a output layer to classify 16 classes.
3. Final architecture is INPUT --> VGG-16 without Top layers(FC) --> Conv Layer --> Maxpool Layer --> 2 FC layers --> Output Layer
4. Trained only new Conv block, FC layers, output layer.

### Model 2

1. Used VGG-16 pretrained network without Fully Connected layers and initilize all the weights with Imagenet trained weights.
2. After VGG-16 network without FC layers, instead of FC layers used conv layers only as Fully connected layer. This conversion will reduce the No of Trainable parameters in FC layers. For example, an FC layer with K=4096 that is looking at some input volume of size 7×7×512 can be equivalently expressed as a CONV layer with F=7,P=0,S=1,K=4096. In other words, we are setting the filter size to be exactly the size of the input volume, and hence the output will simply be 1×1×4096 since only a single depth column “fits” across the input volume, giving identical result as the initial FC layer.
3. Final architecture will be VGG-16 without FC layers(without top), 2 Conv layers identical to FC layers, 1 output layer for 16 class classification. INPUT --> VGG-16 without Top layers(FC) --> 2 Conv Layers identical to FC --> Output Layer
4. Trained only last 2 Conv layers identical to FC layers, 1 output layer. 

### Model 3 

1. Used same network as Model-2 'INPUT --> VGG-16 without Top layers(FC) --> 2 Conv Layers identical to FC --> Output Layer' and train only Last 6 Layers of VGG-16 network, 2 Conv layers identical to FC layers, 1 output layer.
