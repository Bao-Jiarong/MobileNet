## MobileNet Implementation
This repository is about MobileNet in Tensorflow 2.  
I used tf.keras.Model and tf.layers.Layer instead of tf.keras.models.Sequential.  
This allows us to customize and have full control of the model.  
I also used custom training instead of relying on the fit() function.  
In case we have very huge dataset, I applied online loading (by batch) instead of loading the data completely at the beginning. This will eventually not consume the memory.  

#### The Applications of MobileNet
<p></p>
<center>  
<img src="img/7.png" align="center" width="700" height="300"/>
</center>

Image is taken from [source](https://arxiv.org/pdf/1704.04861.pdf)   

#### The Block Architecture
<p></p>
<center>   
<img src="img/2.png" width="500" height="300"/>   
</center>

<p></p>
<center>   
<img src="img/11.jpg" width="500" height="300"/>   
</center>

Images are taken from [source](https://arxiv.org/pdf/1704.04861.pdf)   

#### The MobileNet Architecture
<p></p>
<center>   
<img src="img/3.png" width="500" height="600"/>   
</center>

Image is taken from [source](https://arxiv.org/pdf/1704.04861.pdf)   
### Training on MNIST
<p></p>
<center>
<img src="img/mnist.png" width="400" height="350"/>
</center>

### Requirement
```
python==3.7.0
numpy==1.18.1
```
### How to use
Training & Prediction can be run as follows:    
`python train.py train`  
`python train.py predict img.png`  


### More information
* Please refer to the original paper of MobileNet [here](https://arxiv.org/pdf/1704.04861.pdf) for more information.

### Implementation Notes
* **Note 1**:   
Since datasets are somehow huge and painfully slow in training ,I decided to make number of filters variable. If you want to run it in your PC, you can reduce the number of filters into 32,16,8,4 or 2. (64 is by default). For example:  
`model = mobilenet.MobileNet((113, 113, 3), classes = 10, filters = 32)`

* **Note 2** :   
You can also make the size of images smaller, so that it can be ran faster and doesn't take too much memories.

### Result for MNIST:   
* Learning rate = 0.002
* Batch size = 32  
* Optimizer = Adam   
* Filters = 64
* epochs = 2

Name |  Training Accuracy |  Validation Accuracy  |
:---: | :---: | :---:
MobileNet | 89.44% | 90.41%
