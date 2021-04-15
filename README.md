# NVIDIA-GPU-TF.Data-Binary-CDNN
NVIDIA GPU and TF.Data API optimized Convolution Deep Neural Network for Binary Image Classification. Input speed focus with 0.0 input delay on Microsoft Cats V Dogs Dataset

One device strategy and OS.Environ gpu_private thread mode for single GPU optimized computations for a Convolutional Deep Neural Network. 

Mixed precision float policy for increased speed and Jupyter-Lab tensorboard callbacks and implemenation for pipeline bottleneck analysis. 
Resize/rescale, cache, shuffle, batch, augment (trainineg data re-cached after augmentation for input speed), then all TF.Data datasets prefetched with autotuned buffer_size. 

Autotuned number of parallel operations for tf.data.map(map_func) and tf.data.interleave(map_func) (interleave currently commented out due to slower times on my dev machine)

Data Augmentation does not slow down input pipeline by use of implementing tf.data.cache() after resize and rescale layer and then called again to cache only training data after augmentation.

Not much emphasis placed on model accuracy as you'd want to use ResNet transfer learning for classifcation, this was specific to input pipeline speeds utilizng NVIDIA Software and GPU's

Setup to work on a GTX 1060, GTX 1660, and RTX 3080. 
