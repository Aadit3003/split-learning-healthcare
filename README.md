# Split Learning for Healthcare and Threats to Decentralized Learning
This project was done under the guidance of Dr. Vinay Chamola, BITS Pilani, as part of the course EEE F376 in the Second Semester of AY 22-23.

# Brief Description
Split Learning is a type of decentralized neural network training, wherein after a certain 'cut layer' in the network, client networks share only their activations with the server netwrork, without having to share sensitive data, such as medical records or images. The server proceeds with the remaining calculations, and shares the gradients back with the client to finish the training loop.

In this project, we explored three aspects of Split learning. First, we implemented a Split Resnet-34 network and experimented with the number of clients and the cut layer to observe its effects on task performance. Next, we conceptualized and implemented a Split U-Net for semantic segmentation of Chest X-ray images. Finally, we implemented two threat models to Split Learning, wherein malicious actors try to reconstruct the input data from the client networks' activations, and the corresponding defensive techniques.

The code is accordingly organized.

# 1. Split Resnet-34 and Experiments

# 2. Split U-Net and Semantic Segmentation
Dataset:

# 3. Threat Models and Defensive Techniques
2 papers
