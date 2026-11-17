
# Image Classification Using Vision Transformers (ViT) on CIFAR-10

## 📌 Aim

To implement and study a **Vision Transformer (ViT)** model for image classification using the CIFAR-10 dataset. Understand how image patches, self-attention mechanisms, and transformer-based representations enable effective learning from visual data.

---

## 🎯 Learning Outcomes

After completing this experiment, the following concepts are understood:

- Basic principles of Vision Transformers (ViT).
- Image patch extraction and patch embeddings.
- Working of the self-attention mechanism.
- Fine-tuning a pretrained ViT model for image classification.
- Classification of CIFAR-10 images into 10 different categories.
- Visualization and interpretation of self-attention maps.

---

## 📖 Theory

Vision Transformers (ViTs) are deep learning architectures that apply the Transformer architecture, originally developed for sequence modelling, to computer vision tasks.

Unlike Convolutional Neural Networks (CNNs), which extract visual features using convolutional operations, Vision Transformers divide an image into smaller, fixed-size patches and process them as a sequence of tokens.

### How Vision Transformers Work

The major steps involved in a Vision Transformer are:

1. **Image Patching:** The input image is divided into fixed-size, non-overlapping patches.
2. **Patch Embedding:** Each patch is flattened and converted into a vector representation.
3. **Positional Embedding:** Positional information is added to preserve the spatial arrangement of image patches.
4. **Transformer Encoder:** Patch embeddings are passed through transformer encoder layers.
5. **Self-Attention:** The model learns relationships between different image patches and identifies important visual regions.
6. **Classification Head:** The learned representations are used to predict the final image category.

### Self-Attention Mechanism

Self-attention allows each image patch to interact with other patches and determine their importance for the classification task.

It helps the model capture both local and long-range relationships between different regions of an image.

### Why Vision Transformers?

- Capture long-range dependencies between image regions.
- Learn global visual representations.
- Use attention mechanisms to understand important image regions.
- Can be fine-tuned from pretrained models for smaller datasets.

---

## 📂 Dataset: CIFAR-10

The CIFAR-10 dataset is a widely used image classification dataset containing:

| Property | Description |
|---|---|
| Total Images | 60,000 |
| Training Images | 50,000 |
| Testing Images | 10,000 |
| Image Size | 32 × 32 pixels |
| Image Channels | 3 (RGB) |
| Number of Classes | 10 |

### CIFAR-10 Classes

The dataset contains the following 10 categories:

1. Airplane
2. Automobile
3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse
9. Ship
10. Truck

Images are resized and normalized according to the input requirements of the pretrained Vision Transformer.

A suitable subset of the dataset can be used to reduce computational requirements while maintaining class diversity.

---

## 🛠️ Technologies and Libraries Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- PIL (Python Imaging Library)
- Vision Transformer (ViT)

---

## ⚙️ Experimental Configuration

The following configuration is used as the reference setup for this experiment:

| Parameter | Configuration |
|---|---|
| Model Architecture | ViT-Small |
| Dataset | CIFAR-10 |
| Patch Size | 8 × 8 |
| Number of Classes | 10 |
| Unfrozen Transformer Blocks | 12 (All) |
| Loss Function | Cross-Entropy Loss |
| Optimizer | As configured in implementation |
| Input Format | RGB Images |
| Pretrained Model | Vision Transformer |

---

## 🔬 Methodology / Procedure

### 1. Import Required Libraries
Import the necessary libraries, including PyTorch, Torchvision, NumPy, and Matplotlib.

### 2. Dataset Loading
Load the CIFAR-10 training and testing datasets using `torchvision.datasets`.

### 3. Data Preprocessing
- Resize images to the required ViT input resolution.
- Convert images into tensors.
- Normalize images using the pretrained model's mean and standard deviation.

### 4. Define Class Labels
Define the 10 CIFAR-10 class names for classification and visualization.

### 5. Create Dataset Subsets
Select a computationally manageable subset of the dataset while maintaining representation from all 10 classes.

### 6. Create Data Loaders
Create training and testing DataLoaders with an appropriate batch size. Shuffle the training dataset.

### 7. Load Pretrained Vision Transformer
Load a pretrained Vision Transformer model and modify its classification head to predict 10 CIFAR-10 classes.

### 8. Freeze and Unfreeze Layers
Configure the model's trainable parameters according to the experimental setup. Unfreeze all 12 transformer blocks for fine-tuning.

### 9. Define Loss Function
Use Cross-Entropy Loss for the multi-class image classification task.

### 10. Configure Optimizer
Select an appropriate optimizer and learning rate to update the trainable model parameters.

### 11. Model Training
Train the model for a fixed number of epochs using:
- Forward propagation
- Loss calculation
- Backpropagation
- Parameter updates

Track training loss and accuracy.

### 12. Model Evaluation
Evaluate the trained model on the test dataset using evaluation mode and disabled gradient computation.

Calculate the classification accuracy.

### 13. Extract Self-Attention Weights
Extract attention weights from transformer encoder layers to analyze relationships between image patches.

### 14. Visualize Attention Maps
Generate patch-level attention maps and overlay them on selected test images to understand which regions receive greater attention during classification.

---

## 📊 Results and Observations

The experiment demonstrates how a Vision Transformer processes images as sequences of patches and uses self-attention to learn relationships between different image regions.

### Observations

- The input images are divided into smaller patches before being processed.
- Patch embeddings represent the visual information contained in each image patch.
- Positional embeddings preserve spatial information.
- Transformer encoder layers learn relationships between image patches.
- Self-attention maps provide insights into which image regions receive greater attention.
- Fine-tuning a pretrained ViT enables it to perform image classification on the CIFAR-10 dataset.

### Model Performance

| Metric | Result |
|---|---|
| Training Loss | To be filled |
| Training Accuracy | To be filled |
| Test Accuracy | To be filled |
| Number of Epochs | To be filled |

*Note: Replace the placeholders with the actual values obtained from your implementation.*

### Visualizations

Add your generated output images below.

**1. Sample CIFAR-10 Images**

<!-- Add your dataset visualization here -->
![CIFAR-10 Sample Images](images/cifar10_samples.png)

**2. Training Loss and Accuracy**

<!-- Add your training graphs here -->
![Training Performance](images/training_performance.png)

**3. Self-Attention Maps**

<!-- Add your attention visualization here -->
![ViT Attention Maps](images/attention_maps.png)

---

## ▶️ How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/Bishanka93/Image-Classification-using-VisionTransformers.git
```

### 2. Navigate to the Project Directory

```bash
cd ViT-CIFAR10-Image-Classification
```

### 3. Install Dependencies

```bash
pip install torch torchvision numpy matplotlib pillow
```

### 4. Run the Implementation

```bash
python main.py
```

The CIFAR-10 dataset will be downloaded automatically if it is not available locally.

---

## 📚 References

1. Virtual Labs – Transformers in Vision:  
   https://dp-dei.vlabs.ac.in/exp/transformers-vision/theory.html

2. Virtual Labs – Transformers in Vision (Simulation):  
   https://dp-dei.vlabs.ac.in/exp/transformers-vision/simulation.html

3. Dosovitskiy, A. et al. (2021). *An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale.* International Conference on Learning Representations (ICLR).

4. Vaswani, A. et al. (2017). *Attention Is All You Need.* Advances in Neural Information Processing Systems (NeurIPS).

5. Chollet, F. (2021). *Deep Learning with Python*, 2nd Edition. Manning Publications.

---

## ⭐ Conclusion

The experiment successfully demonstrates the application of Vision Transformers (ViT) for image classification using the CIFAR-10 dataset.

It provides an understanding of how images are divided into patches, converted into embeddings, and processed through transformer encoder layers using self-attention mechanisms.

The experiment also demonstrates how pretrained Vision Transformer models can be fine-tuned for image classification and how attention maps can be visualized to interpret the model's focus on different image regions.

Thus, Vision Transformers provide an effective alternative to traditional CNN-based approaches by learning global relationships between image patches.

---

## 🎓 Extra Credit: Knowledge Distillation

Knowledge Distillation involves transferring knowledge from a larger, pretrained **Teacher Model** to a smaller **Student Model**.

The student model learns not only from the original ground-truth labels but also from the predictions (soft targets) generated by the teacher model.

### Reference

PyTorch – Knowledge Distillation Tutorial:  
https://docs.pytorch.org/tutorials/beginner/knowledge_distillation_tutorial.html

---
## 👨‍💻 Author

**Name:** Bishanka Sarma

**Framework:** Hugging Face Diffusers & PyTorch

---

⭐ If you found this project useful, consider giving the repository a star!
