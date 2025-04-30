Model Architecture


Fake News Detection using DeBERTa and CNN

1. Input Processing
Combines Author, Title, and Text into a single input.
Tokenization & Padding ensures uniform sequence length.

2. Feature Extraction
DeBERTa (Transformer-based embeddings) captures deep contextual meaning.
CNN (Convolutional Neural Network) extracts local text patterns.

3. Feature Fusion
Concatenation of DeBERTa and CNN features for richer text representation.

4. Classification Model 
Fully Connected Layers:
Dense (512) → Batch Norm → Dense (256) → Dropout (0.3) → Dense (128) → Output (Sigmoid).

 5. Training & Evaluation
Performance Metrics: Accuracy, Precision, Recall, F1-Score, Confusion Matrix.
![image](https://github.com/user-attachments/assets/bdd88f5f-ee36-45f7-b485-e05994b8f6a1)





Model Architecture deBerta Fine Tuning!
 1. Input Processing
Combines Author, Title, and Text into a single input string.
Uses Hugging Face DeBERTa Tokenizer with truncation and padding to ensure uniform sequence length (e.g., 128).

2. Feature Extraction
DeBERTa (Transformer-based embeddings):
Unfreezes all layers for fine-tuning on the fake news dataset.
Applies mean pooling across all token embeddings, rather than using the [CLS] token alone.


3. Classification Model
Fully Connected Layers:
Dense (512) → Batch Norm → Dropout (0.3) → Dense (256) → Batch Norm → Dropout (0.3) → Dense (128) → Batch Norm → Output (Sigmoid).

4. Training & Evaluation
Training: Binary Cross-Entropy loss, Adam optimizer (learning rate ~1e-5),
Evaluation: Accuracy, Precision, Recall, F1-Score, and a Confusion Matrix to gauge misclassifications.

![image](https://github.com/user-attachments/assets/36d43dd3-6eb6-46f7-8bc2-d54eeb199735)


