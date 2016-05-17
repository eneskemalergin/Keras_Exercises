# How can I run Keras on GPU?

If you are running on the __TensorFlow backend__, your code will automatically run on GPU if any available GPU is detected. If you are running on the __Theano backend__, you can use one of the following methods:

### Method 1: use Theano flags.

```THEANO_FLAGS=device=gpu,floatX=float32 python my_keras_script.py```

> The name 'gpu' might have to be changed depending on your device's identifier (e.g. gpu0, gpu1, etc).

### Method 2: 
set up your ```.theanorc```: 

```BASH
[global]
floatX = float32
device = gpu0

[lib]
cnmem = 1
```

### Method 3: 

manually set ```theano.config.device```, ```theano.config.floatX``` at the beginning of your code:

```Python
import theano
theano.config.device = 'gpu'
theano.config.floatX = 'float32'
```
