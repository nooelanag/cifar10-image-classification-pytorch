# CIFAR-10 Image Classification with PyTorch

Lab session of *Speech, Audio, Image and Video Processing Applications*
(Master's in Telecommunication Engineering, UC3M).

## Contents
- Fully connected networks (MLP) for CIFAR-10, with tanh activations and cross-entropy loss
- Effect of the learning rate (1e-1, 1e-3 and 1e-5) using training/validation curves
- AlexNet-style convolutional network
- Choice of the number of epochs from the validation curves
- Visualization of the filters and activation maps of the first convolutional layer

## Results

**Learning rate (fully connected network, 10 epochs)**

| Learning rate | Validation accuracy | Validation loss |
|---|---|---|
| 1e-1 | 47.9% | 1.70 |
| 1e-3 | 42.4% | 1.72 |
| 1e-5 | 25.2% | 2.14 |

With 1e-5 the network barely learns in 10 epochs (loss close to random guessing, ln 10 ≈ 2.30), 1e-3 is still converging, and 1e-1 learns fastest although it starts to overfit.

**Test set**

| Model | Training | Test accuracy | Test loss |
|---|---|---|---|
| Fully connected network | lr = 1e-1, 10 epochs | 46.66% | 1.74 |
| AlexNet-style CNN | lr = 1e-1, 6 epochs | **73.62%** | 0.78 |

Training the CNN for 15 epochs showed clear overfitting after epoch 6 (the validation loss reaches its minimum, 0.81, and then increases while the training loss keeps decreasing), so 6 epochs were used for the final model.

## How to run
Open the notebook in Google Colab (GPU runtime recommended) and run the cells in order.
CIFAR-10 is downloaded by the notebook, so it is not included in this repository.
Results vary slightly between runs because of the random initialization and minibatch order.

## Notes
The lab statement and the base code were provided by the course instructors.
