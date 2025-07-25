# Emotion Faces Dataset (7 Classes - 224x224)

This repository contains a curated and preprocessed facial emotion dataset with approximately 20,000 images distributed across 7 emotion categories:

- Angry
- Disgust
- Fear
- Happy
- Sad
- Surprise
- Neutral

## 📋 Dataset Description

- Each image contains **exactly one detected face**.
- Faces were detected using **Haar Cascade (OpenCV)**.
- Cropped face regions were resized to **224x224 pixels**.
- Images are stored in folders named after their emotion class.

## 📁 Folder Structure

```
datasetpreprocessed/
├── angry/
├── disgust/
├── fear/
├── happy/
├── sad/
├── surprise/
└── neutral/
```

## 🧰 Usage Example (Keras)

```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator

datagen = ImageDataGenerator(rescale=1./255, validation_split=0.2)

train_generator = datagen.flow_from_directory(
    'datasetpreprocessed',
    target_size=(224, 224),
    batch_size=32,
    class_mode='categorical',
    subset='training'
)

val_generator = datagen.flow_from_directory(
    'datasetpreprocessed',
    target_size=(224, 224),
    batch_size=32,
    class_mode='categorical',
    subset='validation'
)
```

## ⚙️ Preprocessing Pipeline

Images were processed using the following script:
- Haar Cascade for face detection
- Filter: only one face per image
- Resize to 224x224
- Save to class folders

## 📄 License

This dataset was built from public sources and is intended for **educational and research purposes** only.
