# fire-prediction
Develop a deep learning model to classify images into Fire and Non-Fire categories using a convolutional neural network (CNN) architecture, specifically MobileNetV2.
Fire Detection Using CNN (MobileNetV2)
This project demonstrates a fire vs. non-fire image classification model built using TensorFlow/Keras and trained on an open-source dataset.
The goal is to showcase a complete deep learning workflow — data preparation, training, evaluation, and real-world testing — using a lightweight and efficient model architecture.

📂 Dataset
A publicly available Kaggle dataset was used for training/testing.
It contains Fire and Non-Fire images.
Since datasets are large, they are stored externally.
👉 Dataset (Google Drive):
https://drive.google.com/drive/folders/13jLJllVwIl2-zlNM65t97T_pcA7VoPuM?usp=drive_link
Folder structure used in training:
Data/
   Train_Data/
      Fire/
      Non_Fire/
   Test_Data/
      Fire/
      Non_Fire/

Images are automatically loaded using Keras ImageDataGenerator.

🧠 Model Architecture
The model uses MobileNetV2 pretrained on ImageNet with the top layers removed.
A custom classifier head is added:


GlobalAveragePooling2D


Dense (128) + ReLU


Dropout (0.3)


Dense (1) + Sigmoid


Loss: Binary Crossentropy
Optimizer: Adam
Batch Size: 32
Epochs: 5
This gives a fast and lightweight model suitable for real-time applications.

🚀 What I Did
This project demonstrates:
✔ Data Loading & Preprocessing
Using ImageDataGenerator with:


Rescaling


Validation split


Augmentation


✔ Model Training
Trained MobileNetV2 for 5 epochs on ~3,600 images.
Achieved strong validation accuracy (~95–96%).
✔ Model Saving & Loading
Saved the final model as:
fire_detection_mobilenetv2.h5

✔ Testing on Independent Images
Tested on 50 unseen images (fire & non-fire).
Results printed for each test image.

🔍 Transparency / Limitations
To remain academically honest, here are the important limitations:
🔸 1. Some Fire Images Were Misclassified
The model struggled with:


small/low-intensity flames


images with orange lighting similar to fire


very bright environments


🔸 2. Dataset Size Could Be Larger
A bigger dataset would improve robustness.
🔸 3. Needs More Regularization
More epochs + early stopping + augmentation would help.
🔸 4. Real-world performance may vary
Different lighting, camera quality, and smoke levels affect predictions.

📈 How to Improve This Model
If continuing this project later, you can upgrade it by:


Using EfficientNetB1/B3


Training for 20–30 epochs with early stopping


Adding RandomBrightness, Cutout, Mixup


Collecting real CCTV fire footage


Converting the model to TensorFlow Lite for mobile



🛠️ How to Run the Project (Google Colab)


Open the notebook.


Mount Google Drive.


Place the data exactly as:


/content/drive/MyDrive/Data/Train_Data
/content/drive/MyDrive/Data/Test_Data



Run the training cells.


Model will save as:


/content/fire_detection_mobilenetv2.h5



Run the testing script.


🏁 Conclusion
This project successfully demonstrates a complete fire-detection pipeline using deep learning.
While not perfect, it shows clear capability to classify fire vs. non-fire and provides a strong foundation for further improvement.

