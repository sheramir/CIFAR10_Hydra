# CIFAR10 Image Classification with PyTorch Lightning

This project implements a modular image classification system for the CIFAR10 dataset using PyTorch Lightning and Hydra. The architecture is designed to be flexible, allowing easy experimentation with different models and configurations.

## Project Structure

.
├── configs/
│ ├── config.yaml
│ ├── cifar10_classification.yaml
│ ├── sgd.yaml
│ └── cifar10_model.yaml
├── data_modules/
│ └── cifar10.py
├── models/
│ └── cifar10_model.py
├── tasks/
│ └── cifar10_task.py
├── train.py
└── README.md


## Features

- Modular architecture using PyTorch Lightning
- Configuration management with Hydra
- TensorBoard logging support
- Model checkpointing
- Easy model backbone swapping
- Support for different optimizers and loss functions

## Requirements

pytorch
pytorch-lightning
torchvision
hydra-core
omegaconf


## Installation

git clone https://github.com/sheramir/CIFAR10_Hydra

pip install -r requirements.txt


## Usage

### Training

To train the model with default configurations:
bash
python train.py


To override specific configurations:

bash
python train.py model=resnet18 optimizer=adam

### Monitoring

Monitor training progress using TensorBoard:

bash
tensorboard --logdir tb_logs


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

bash
python train.py model.backbone=resnet34


### Training on MNIST

The project includes support for MNIST classification through configuration overrides:

bash
python train.py task=mnist_task data_module=mnist

