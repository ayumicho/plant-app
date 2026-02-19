# Baselines

Baselines establish a performance reference before introducing more complex models. They help contextualize results, making it possible to assess whether a model is genuinely learning or simply getting lucky, and set realistic expectations for what the task demands.

Three baselines were defined for this project: a random guess baseline, a neural network baseline, and a human-level performance baseline.

---

## Random Guess Baseline

The random guess baseline reflects the accuracy a model would achieve if it assigned class labels completely at random, without learning anything from the data. It acts as an absolute floor — any model worth deploying must comfortably exceed this.

The dataset contains **6 classes**. Assuming balanced class distribution, the calculation is straightforward:

$$\text{Random Guess Accuracy} = \frac{100}{6} \approx 16.67\%$$

**Result: ~17%**

Any model performing at or near 17% offers no advantage over chance.

---

## MLP Baseline

A Multilayer Perceptron was built as a simple neural network reference point. Because an MLP treats input as a flat vector, it has no spatial awareness of the image, making it a useful baseline to later contrast against architectures designed for visual data.

### Architecture

The model was built using Keras Sequential API. Input images were flattened from their original 3D shape before being passed through a series of fully connected Dense layers with ReLU activations, ending in a 6-unit Softmax output layer for multi-class classification.

| Layer | Output Shape | Parameters |
|---|---|---|
| Flatten | (None, 49152) | 0 |
| Dense (512, ReLU) | (None, 512) | 25,166,336 |
| Dense (512, ReLU) | (None, 512) | 262,656 |
| Dense (256, ReLU) | (None, 256) | 131,328 |
| Dense (256, ReLU) | (None, 256) | 65,792 |
| Dense (128, ReLU) | (None, 128) | 32,896 |
| Dense (6, Softmax) | (None, 6) | 774 |

**Total parameters: 25,659,782**

The large parameter count is primarily driven by the first Dense layer, which receives the fully flattened image input (128×128×3 = 49,152 features).

### Training Process

The model was compiled with categorical cross-entropy loss and the Adam optimizer. Training ran for up to 64 epochs with a batch size of 32 and a 20% validation split. Early stopping was applied with a patience of 3, monitoring validation loss and restoring the best weights — in practice, training halted at epoch 9 when validation loss began increasing consistently.

### Learning Curves

Training loss steadily decreased across epochs, but validation loss began diverging from epoch 6 onward, indicating the model started overfitting to the training set. Early stopping successfully interrupted training before performance degraded further.

### Results

| Metric | Value |
|---|---|
| Test Loss | 1.782 |
| Test Accuracy | **26.67%** |

**Result: ~27%**

The MLP achieved 26.67% test accuracy. While this surpasses the random guess baseline of 17%, the improvement is modest. This is expected, flattening image data discards all spatial structure, so the model has no mechanism to learn features like edges, textures, or shapes. This result motivates the use of convolutional architectures in subsequent steps.

> **Note:** Look at this notebook for the full code and training details: [Basic Multilayer Perceptron Accuracy](/notebooks/basic_MLP_accuracy.ipynb)

---

## Human-Level Performance Baseline

Human-level performance was measured to understand what a person with access to reference material, but no prior expertise, can realistically achieve on this classification task. This acts as a practical upper-bound target for the model.

### Survey Design

A Microsoft Forms questionnaire was prepared with **12 questions**, two per class, each presenting an image and asking respondents to identify the correct plant species from the available labels. Since plant identification is not common knowledge, respondents were given a **reference cheat sheet** to ensure the evaluation reflected informed effort rather than prior expertise.

![Plant Species Cheat Sheet](/images/plant_species_cheat_sheet.png)

### Results

**20 responses** were collected from peers. Individual accuracy scores ranged from **33% to 100%**, reflecting natural variation in how carefully respondents engaged with the material.

The average across all respondents gives the human-level performance baseline:

**Result: 77%**

The wide spread between the lowest and highest individual scores suggests that even with a cheat sheet, the task carries meaningful difficulty, some plant species are visually similar enough to cause confusion.

---

## Baseline Comparison

| Baseline | Accuracy | Notes |
|---|---|---|
| Random Guess | ~17% | Lower bound, 6 equally likely classes |
| MLP | ~27% | Simple neural network, no spatial awareness |
| Human-Level Performance | 77% | Average across 20 peer respondents |

The range between 17% and 77% defines the performance window the model should be evaluated against. Surpassing the random guess baseline confirms the model is learning. Approaching or exceeding human-level performance would indicate it has mastered the task to a meaningful degree.