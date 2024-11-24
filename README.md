# Sign Language to Speech Conversion using Machine Learning

This project is a **Sign Language to Speech Conversion System** that translates American Sign Language (ASL) gestures into text and spoken words. It leverages **MediaPipe**, **Machine Learning**, and a custom-built graphical user interface (GUI) for real-time recognition and speech synthesis.

---

## 📝 Project Overview

1. **Data Collection**: 
   - Captures images of ASL gestures using a webcam.
   - Supports 38 classes: A-Z, 0-9, space, and full stop.
   - Stores images in organized class-wise directories.

2. **Feature Extraction**: 
   - Uses **MediaPipe Hands** to extract hand landmarks from images.
   - Converts images into numerical feature vectors for model training.

3. **Model Training**: 
   - Trains a **Random Forest Classifier** to recognize ASL gestures.
   - Achieves high accuracy with a robust feature set.

4. **Real-Time Inference**: 
   - Recognizes gestures in real time using a webcam.
   - Forms words and sentences based on recognized gestures.
   - Provides speech output for constructed sentences using `pyttsx3`.

---

## 🎯 Features

- **Real-Time Recognition**: Converts live webcam feed into recognized gestures.
- **Robust Prediction**: Implements stabilization for accurate gesture recognition.
- **Word and Sentence Formation**: Automatically forms words and sentences with proper segmentation (space and full stop gestures).
- **Text-to-Speech Conversion**: Speaks out the recognized text for better accessibility.
- **User-Friendly GUI**: Displays the current alphabet, word, and sentence in real time.

---

## 🛠️ How to Use

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/sign-language-to-speech.git
   cd sign-language-to-speech
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. **Data Collection**:
   - Run `collect_imgs.py` to collect gesture images for each class.
   - Use a webcam to capture images for training.

4. **Feature Extraction**:
   - Run `create_dataset.py` to preprocess the collected images.
   - The dataset will be saved as `data.pickle`.

5. **Model Training**:
   - Run `train_classifier.py` to train the gesture recognition model.
   - The trained model will be saved as `model.p`.

6. **Real-Time Inference**:
   - Run `main.py` to start the real-time gesture recognition system.
   - The GUI will launch automatically.

---

## 🔧 Tech Stack

- **Languages**: Python
- **Libraries**: MediaPipe, OpenCV, Tkinter, Pyttsx3, Scikit-learn
- **Machine Learning Model**: Random Forest Classifier

---

## 📂 Project Structure

```
sign-language-to-speech/
├── collect_imgs.py          # Data collection script
├── create_dataset.py        # Feature extraction and dataset creation script
├── train_classifier.py      # Model training script
├── main.py  # Real-time inference script with GUI
├── model.p                  # Trained model file
├── data/                    # Directory for collected images
└── README.md                # Project documentation
```

---

## 🤝 Team Members

1. **[Tanmay Jivnani]((https://github.com/tanmayJivnani)**
2. **[Shravani Verma]((https://github.com/Shravknowscoding)**
3. **Aishwarya Shendkar**

---

## 📋 Future Enhancements

- Expand the system to support additional gestures or full words.
- Improve model accuracy with advanced deep learning techniques.
- Add multi-language support for text-to-speech conversion.

---

## 📝 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
