# evt-MNIST
This is an event-driven version of MNIST dataset which can be used to evaluating spiking neural network's accuracy. I used Poisson distribution to generating spike trains of images of MNIST dataset to extracting a spike-based dataset from a frame-based dataset respecting to intensity of each pixel of images. Using this method, I generate an event-driven dataset of MNIST called evt-MNIST which is contained all the test and train images of MNIST dataset. There is two videos which playback the spike generation corresponding to pixels density. You can see pixels with more density (the brighter pixels) have more spikes/sec. I assumed 100ms for pixels representation. In fact I used the pixels intensity as the intensity of stimuli which are clamped on the inputs of our SNN during of simulation. The maximum rate for completely white pixels is 1000 Hz (100 spikes in 100 ms).

-------------
Download evt-MNIST from my GDrive:
https://drive.google.com/open?id=0B0dQCWHI1FhDdDRhcnZVc1M5VEk
Please download and decompress files. Load each file separately in Matlab and merge them:

load 'evtMNIST_1.mat'
data=evt_MNIST_train_x;
for batch=2:24
  load ['evtMNIST_' int2str(2) '.mat'];
  data=[data;evt_MNIST_train_x];
end



Please be free to ask me any question about this dataset
