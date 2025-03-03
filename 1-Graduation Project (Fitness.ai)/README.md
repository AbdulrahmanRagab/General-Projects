# 🏋️‍♂️ Fitness.ai - AI-Based Exercise Classification and Tracking

## Table of Contents
- [🌟 Overview](#-overview)
- [🛠️ Technologies Used](#-technologies-used)
- [🎯 Project Objectives](#-project-objectives)
- [📹 Video Overview](#-video-overview)
- [🚀 Key Features](#-key-features)
- [🛠️ Methodology](#-methodology)
- [🧠 Model Training and Evaluation](#-model-training-and-evaluation)
- [🎉 Conclusion](#-conclusion)
- [🙏 Acknowledgments](#-acknowledgments)
- [🔮 Future Work](#-future-work)
- [🛠️ How to Use](#-how-to-use)

---

## 🌟 Overview
**Fitness.ai** is an AI-powered application designed to classify human exercises and track user performance in real-time. The application leverages advanced machine learning techniques, specifically **pose detection** and **multinomial logistic regression**, to accurately identify and monitor various fitness and physical therapy exercises. The project aims to revolutionize exercise classification and tracking by providing users with real-time feedback, personalized monitoring, and convenient accessibility.

---

## 🛠️ Technologies Used

### Programming Language
- **Python**  
  ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### Frameworks and Libraries
- **MediaPipe** (for pose detection)  
  ![MediaPipe](https://img.shields.io/badge/MediaPipe-FF6F00?style=for-the-badge&logo=mediapipe&logoColor=white)
- **Pandas** (for data manipulation)  
  ![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
- **NumPy** (for numerical computations)  
  ![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
- **OpenCV** (for video processing)  
  ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
- **Scikit-learn** (for machine learning)  
  ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
- **Plotly** (for data visualization)  
  ![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
- **Matplotlib** (for data visualization)  
  ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)

---

## 🎯 Project Objectives
1. **🏋️‍♀️ Exercise Classification**: Accurately classify different human exercises using pose detection and machine learning.
2. **🔢 Repetition Tracking**: Track the number of repetitions for each exercise to help users monitor their progress.
3. **📊 Personalized Monitoring**: Provide personalized feedback and insights based on the user's performance over time.
4. **📱 Accessibility**: Ensure the application is user-friendly and accessible across multiple devices (smartphones, tablets, computers).

---

## 📹 Video Overview
Watch the **Fitness.ai** video overview to see the application in action:
- [Fitness.ai Video Overview](https://tinyurl.com/mr4bdc6n)

---

## 🚀 Key Features
### 1. **Exercise Classification**
   - Utilizes pose detection and classification techniques to recognize and categorize various exercises.
   - Provides real-time feedback on exercise form and technique.

### 2. **Repetition Tracking**
   - Tracks the number of repetitions for each exercise.
   - Helps users set goals and maintain consistency in their routines.

### 3. **Personalized Exercise Monitoring**
   - Offers tailored feedback and insights based on the user's performance.
   - Recommends modifications or variations of exercises to enhance effectiveness.

### 4. **Accessibility and Convenience**
   - Designed to be user-friendly and accessible on multiple devices.
   - Allows users to perform exercises at home or in the gym without the need for a fitness professional.

### 5. **Real-Time Feedback**
   - Provides real-time feedback on exercise counts and duration.
   - Ensures users are performing exercises correctly and safely.

### 6. **Video Playlist and Upload**
   - Includes a playlist of exercise videos for guidance.
   - Allows users to upload custom exercise videos from their device.

### 7. **User-Friendly Interface**
   - Developed using the **Flutter framework** for a seamless and intuitive user experience.
   - Easy navigation to access exercise playlists, camera, and video upload features.

---

## 🛠️ Methodology
### 1. **Data Collection and Processing**
   - **🎥 Video Recording**: Recorded exercise videos from multiple sources, including **physitrack.com** and collaboration with a physiotherapy center.
   - **📍 Landmark Extraction**: Used **OpenCV** and **MediaPipe** to extract 33 body landmarks from the videos.
   - **🏷️ Manual Labeling**: Implemented a user interaction mechanism to manually label exercise classes for the extracted landmarks.

### 2. **Model Selection**
   - **🤖 Initial Models**: Explored models like **Artificial Neural Network (ANN)**, **Random Forest Classifier**, and **Gradient Boosting Classifier**.
   - **⚠️ Generalization Issues**: These models faced challenges in generalizing to unseen data, leading to suboptimal performance.

### 3. **Multinomial Logistic Regression**
   - **✅ Final Model**: Chose **Multinomial Logistic Regression** for its ability to handle multiple classes and provide accurate predictions.
   - **📊 Evaluation Metrics**: Achieved an accuracy of **90%** with high precision, recall, and F1 scores.
   - **🌐 Generalization**: The model demonstrated strong generalization capabilities, making it suitable for real-world exercise classification.

### 4. **Application Development**
   - **📱 Framework**: Developed the mobile application using **Flutter** for a user-friendly interface.
   - **✨ Features**: Integrated real-time pose detection, exercise counters, and video playback functionalities.

---

## 🧠 Model Training and Evaluation
### 1. **Dataset**
   - The dataset consists of **13 exercise classes** with varying counts of samples:
     ```
     frontleg_down    94
     frontleg_up      55
     squat_down       51
     squat_up         50
     shoulders        43
     kegel_down       36
     kegel_up         34
     deadlift_down    24
     deadlift_up      20
     pushup_up        20
     pushup_down      16
     shoulder_down    14
     shoulder_up      12
     ```

### 2. **Model Training**
   - **Multinomial Logistic Regression** was used with custom class weights to handle class imbalance.
   - The model was trained with the following parameters:
     ```python
     model = LogisticRegression(multi_class='multinomial', solver='lbfgs', class_weight=class_weights, max_iter=1000)
     ```

### 3. **Evaluation Metrics**
   - **Accuracy**: 90.30%
   - **Precision**: 91.10%
   - **Recall**: 90.30%
   - **F1 Score**: 89.78%


### 4. **Confusion Matrix**
   - The confusion matrix provides insights into the model's performance across different exercise classes.


---

## 🎉 Conclusion
**Fitness.ai** represents a significant advancement in the field of fitness and physical therapy by leveraging AI technology for exercise classification and tracking. The application provides users with real-time feedback, personalized monitoring, and convenient accessibility, making it a valuable tool for individuals looking to improve their fitness or engage in effective physical therapy.

---

## 🙏 Acknowledgments
- **👨‍🏫 Supervisor**: Dr. Mohamed El-Saeed for guidance and support.
- **🏥 Physiotherapy Center**: For collaboration and exercise recommendations.
- **🛠️ MediaPipe Framework**: For providing accurate and efficient pose detection capabilities.

---

## 🔮 Future Work
- Expand the range of exercises supported by the application.
- Incorporate more advanced machine learning models for improved accuracy.
- Develop additional features such as progress tracking over time and integration with wearable devices.

---

## 🛠️ How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/AbdulrahmanRagab/Fitness.ai.git
