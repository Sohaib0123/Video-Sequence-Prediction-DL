# Predicting and Generating Video Sequences Using Deep Learning

## Project Overview  
This project focuses on predicting future video frames using deep learning. We implement and compare three models—ConvLSTM, PredRNN, and a Transformer-based model—to generate coherent video sequences from the UCF101 dataset. The goal is to simulate the continuation of an action based on short input sequences, with applications in video synthesis, animation, and scene prediction.  

## Dataset  
- **Source:** [UCF101 Action Recognition Dataset](https://www.kaggle.com/datasets/matthewjansen/ucf101-action-recognition/data)  
- **Selected Classes:** PushUps, PullUps, BenchPress, Lunges, WallPushups  
- **Preprocessing:**  
  - Frames resized to **64×64 pixels**  
  - Converted to **grayscale**  
  - Input sequence: **30 frames** → Target sequence: **15 frames**  

##  Process of the Project  
### 1. Data Collection & Preprocessing
- Downloaded the **UCF101 dataset** and selected specific action classes with consistent motion.  
- Resized frames to **64×64 pixels** and converted them to **grayscale** for reduced computational complexity.  
- Split videos into input (30 frames) and target (15 frames) sequences.  
- Prepared data loaders for training and validation with appropriate batch sizes.  

### 2. Model Implementation
We implemented and trained **three different deep learning models** from scratch:  
- **ConvLSTM** - Uses convolutional LSTMs to capture spatial-temporal dependencies.  
- **PredRNN** - Enhances recurrent memory flow for better temporal modeling.  
- **Transformer-based Model** - Uses attention mechanisms for long-term dependencies.  
  
Each model was trained on the prepared dataset using **MSE and SSIM as evaluation metrics**.  

### 3. Model Training & Evaluation  
- **ConvLSTM:** Captured short-term dependencies but struggled with long-term motion consistency.  
- **PredRNN:** Achieved the best performance with **smooth frame transitions and high temporal coherence**.  
- **Transformer-based Model:** Had difficulty maintaining sequential motion patterns but showed potential for attention-based improvements.  
 

### 4. Video Generation
- Implemented a function using **OpenCV** and **moviepy** to convert predicted frames into smooth video clips.  
- Visualized generated sequences to analyze model performance.  

### 5. User Interface Development
Developed a **Gradio-based web UI** to allow users to:  
 Upload/select sample videos  
 Run all models and display generated frames  
 Compare runtime inference results  

### 6. Evaluation Metrics  
To assess the accuracy and effectiveness of frame prediction, we used the following evaluation metrics:
- **Mean Squared Error (MSE):** Measures pixel-wise prediction error between actual and generated frames.
- **Structural Similarity Index (SSIM):** Evaluates perceptual similarity between frames, considering luminance, contrast, and structure.
- **Qualitative Analysis:** Visual inspection of generated frames to assess coherence, smoothness, and realism.

### Report & Documentation
- Conducted a **comparative analysis** of the models based on frame quality, inference time, and computational efficiency.  
- Documented challenges, findings, and future improvements.  

