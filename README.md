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

## 📚 Sources

This dataset was created by merging and preprocessing images from the following sources:

- **FER2013**: Publicly available facial expression dataset.
- **Own collected images**: Additional samples manually curated and labeled.

All data was cleaned, face-detected, and resized to 224x224 for model compatibility.

## 📄 License

This dataset was built from public sources and is intended for **educational and research purposes** only.
