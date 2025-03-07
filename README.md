# CIFAR10 Image Classification with PyTorch Lightning

This project implements a modular image classification system for the CIFAR10 dataset using PyTorch Lightning and Hydra. The architecture is designed to be flexible, allowing easy experimentation with different models and configurations.

## Project Structure

.</br>
├── configs/</br>
│ ├── config.yaml</br>
│ ├── cifar10_classification.yaml</br>
│ ├── sgd.yaml</br>
│ └── cifar10_model.yaml</br>
├── data_modules/</br>
│ └── cifar10.py</br>
├── models/</br>
│ └── cifar10_model.py</br>
├── tasks/</br>
│ └── cifar10_task.py</br>
├── train.py</br>
└── README.md</br>


## Features

- Modular architecture using PyTorch Lightning
- Configuration management with Hydra
- TensorBoard logging support
- Model checkpointing
- Easy model backbone swapping
- Support for different optimizers and loss functions

## Requirements

pytorch</br>
pytorch-lightning</br>
torchvision</br>
hydra-core</br>
omegaconf</br>


## Installation

```
git clone https://github.com/sheramir/CIFAR10_Hydra

pip install -r requirements.txt
```


## Usage

### Training

To train the model with default configurations:
bash
python train.py


To override specific configurations:

`python train.py model=resnet18 optimizer=adam`

### Monitoring

Monitor training progress using TensorBoard:

`tensorboard --logdir tb_logs`


## Project Components

- **Data Module**: Handles CIFAR10 dataset loading and preprocessing
- **Model**: Implements the neural network architecture
- **Task**: Manages training logic, loss computation, and metrics
- **Configs**: Hydra configuration files for different components

## Model Performance

The model is evaluated using:
- Cross Entropy Loss
- Accuracy metric
- Validation accuracy for model checkpointing

## Configuration

The project uses Hydra for configuration management. Key configuration files:

- `config.yaml`: Main configuration file
- `cifar10_classification.yaml`: Dataset and training parameters
- `sgd.yaml`: Optimizer configuration
- `cifar10_model.yaml`: Model architecture configuration

## Extending the Project

### Using Different Backbones

You can easily swap model backbones through the configuration:

`python train.py model.backbone=resnet34`


### Training on MNIST

The project includes support for MNIST classification through configuration overrides:

`python train.py task=mnist_task data_module=mnist`

