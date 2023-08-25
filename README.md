# Split Learning for Healthcare and Threats to Decentralized Learning
This project was done under the guidance of Dr. Vinay Chamola, BITS Pilani, as part of the course EEE F376 in the Second Semester of AY 22-23.

# Brief Description
Split Learning is a type of decentralized neural network training, wherein after a certain 'cut layer' in the network, client networks share only their activations with the server network, without having to share sensitive data, such as medical records or images. The server proceeds with the remaining calculations and shares the gradients back with the client to finish the training loop.

In this project, we explored three aspects of Split learning. First, we implemented a Split Resnet-34 network and experimented with the number of clients and the cut layer to observe its effects on task performance. Next, we conceptualized and implemented a Split U-Net for semantic segmentation of Chest X-ray images. Finally, we implemented two threat models to Split Learning, wherein malicious actors try to reconstruct the input data from the client networks' activations, and the corresponding defensive techniques.

The code is accordingly organized.

# 1. Split Resnet-34 and Experiments
**Dataset:** [Diabetic Retinopathy](https://www.kaggle.com/datasets/tanlikesmath/diabetic-retinopathy-resized) (Retinal Images; 2-class classification)

**Model Details:** 
- Resnet-34
- 1000 train images, 200 test images
- Epochs = 20
- Cut_Layer = 3 (default)
- Number of Clients = 2 (default)
- learning rate: 0.001
- Loss Function: Cross-Entropy Loss
- Optimizer: Adam (lr = 0.01)

  <img src="https://github.com/Aadit3003/split-learning-healthcare/blob/8b721d004e14c7fb13f3ac55648ce51e08fc23e9/Assets/Images/activations.png" width="600" />
  The successive activations of the client model, starting with the input image up to the data shared with the server network.

**Experiments:**
- Vary Cut-Layer (2, 3, 5, 7) to observe differences in test accuracies
- Vary Number of Clients (1, 2, 3, 4, 6) to observe differences in test accuracies

  <img src="https://github.com/Aadit3003/split-learning-healthcare/blob/8b721d004e14c7fb13f3ac55648ce51e08fc23e9/Assets/Images/cut.png" width="600" />
  The training loss of two client networks as the cut-layer is varied.

# 2. Split U-Net and Semantic Segmentation
**Dataset:** [Lung Segmentation from Chest X-rays](https://www.kaggle.com/code/nikhilpandey360/lung-segmentation-from-chest-x-ray-datasethttps://www.kaggle.com/code/nikhilpandey360/lung-segmentation-from-chest-x-ray-dataset) (Semantic Segmentation)

# 3. Threat Models and Defensive Techniques
Threat Models:
- Feature-Space Hijacking Attack (FSHA) - [Pasquini et al. (2021) 'Unleashing the Tiger: Inference Attacks on Split Learning'](https://arxiv.org/abs/2012.02670)
- Adversarial Reconstruction Attack (ADRA)

