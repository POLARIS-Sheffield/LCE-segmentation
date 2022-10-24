# LCE-segmentation

## Using the DL trained model

The model was trained using the Niftynet framework; instructions are provided below to allow researchers to utilize the trained DL model. The instructions given here will largely follow the instructions given at https://github.com/NifTK/NiftyNet.

## Installation 

```
pip install “tensorflow==1.15.*”
pip install niftynet
```

We have provided a configuration file that can be used for inference on paired hyperpolarized gas MRI and 1H-MRI scans. We highlight the main parameters in the configuration file required for inference that are specific to the primary user.

## Paths

The user must provide paths to folders containing the hyperpolarized gas and proton MRI scans and a path to the location to save the outputted segmentations.

```
[HPGas]

path_to_search = #path to hyperpolarized gas MRI scans

[Proton]

path_to_search = #path to proton MRI scans
save_seg_dir = #path to output location
```

## Computational resources

Depending on the computational resources available to the individual researcher, the following parameters will need to be amended:

```
num_threads = 0
num_gpus = 0
```

In our investigations, we used a single GPU with two threads.

## Running inference

The following command can be used to run inference by indicating the path to the configuration file:

```
net_segment inference -c /path_to_config/config_inference.ini
```
