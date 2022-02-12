# Introduction to PyTorch

General steps

1. Create dateset with `Dataset` and `DataLoader`. [Official tutorial](https://pytorch.org/tutorials/beginner/basics/data_tutorial.html)
2. Build model with `nn.Module` or `pl.LightningModule`. [`nn.Module` tutorial](https://pytorch.org/tutorials/beginner/basics/buildmodel_tutorial.html) and [PyTorch Lightning tutorial](https://pytorch-lightning.readthedocs.io/en/stable/common/lightning_module.html)
    - Constructor `__init__()`: Define components e.g. `nn.Linear`, `nn.Conv2d`
    - Forward propagation `__forward__()`: Define forward propagation behavior
    - Training loop `training_step()`: return loss
    - Evaluation loop `validation_step()`: log evaluation metrics
3. Optimize the model
    - Iterate over batches of data
    - Calculate loss on one batch (`training_step()`)
    - Use the optimizer (e.g. SGD, Adam) to update model's weights
    - At the end of every epoch, run evaluation loop on validation data
    - Repeat for N epochs
4. Evaluate the model
    - More comprehensive evaluation metrics. Sometimes training behavior is different from testing/inference behavior

Extra stuff

- Use OpenCV to read images
- Log metrics with Weight and Biases `wandb`
- Use pre-trained CNN from `torchvision`
