# 🌉 Multimodal Bi-Directional Accessibility Bridge

**A real-time AI tool bridging the gap between Deaf/Mute and Blind individuals.**

This project runs entirely in the browser via **Google Colab**. It uses Computer Vision and Speech Recognition to translate between **Sign Language** and **Spoken English** in real-time.

## 🎯 The Problem Solved
Direct communication between a Deaf/Mute person and a Blind person is incredibly difficult:
* The Deaf person signs, but the Blind person cannot see it.
* The Blind person speaks, but the Deaf person cannot hear it.

**This AI acts as the middle-man:**
1.  **Visual-to-Auditory:** It watches the Deaf user's hands and **Speaks** the translation for the Blind user.
2.  **Auditory-to-Visual:** It listens to the Blind user's voice and **Displays** sign language images for the Deaf user.

---

## 🚀 How to Run (Google Colab)

**Prerequisites:**
* Google Chrome (Required for Web Speech API).
* A webcam and microphone.

**Installation Steps:**
1.  **Open the Notebook:** Load the `OmniComm.ipynb` file in Google Colab.
2.  **Install Libraries:** Run the first cell to install MediaPipe:
    ```python
    !pip install mediapipe opencv-python-headless
    ```
3.  **Generate Assets:** Run the "Database Generator" script to create the sign language flashcards in memory.
4.  **Start the Bridge:** Run the main `video_stream` code block.
5.  **Grant Permissions (CRITICAL):**
    * A popup will appear asking for permissions.
    * You **MUST** click **"Allow"** for both **Camera** and **Microphone**.
    * *Mac Users:* If blocked, check your System Settings -> Privacy -> Microphone.

---

## 🎮 User Guide

### 🖐️ Mode A: Sign-to-Speech (Deaf -> Blind)
* **User:** Deaf/Mute person.
* **Action:** Perform a hand gesture to the camera.
* **Result:**
    1.  The AI detects the sign (e.g., "HELLO").
    2.  It builds a sentence on screen.
    3.  After a pause (4s), it **reads the sentence aloud** for the Blind user.
* **Supported Signs:**
    * `HELLO` (Open Palm)
    * `YES` (Thumbs Up)
    * `NO` (Index/Middle tap thumb)
    * `YOU` (Pointing)
    * `LOVE` (Spider-man sign)
    * `PEACE` (V Sign)
    * `OK` (Thumb touches Index)
    * `CLEAR` (Fist - erases sentence)

### 🗣️ Mode B: Speech-to-Sign (Blind -> Deaf)
* **User:** Blind person.
* **Action:** Click the **"🎤 Speak Back"** button and speak a sentence (e.g., "Hello friend").
* **Result:**
    1.  The AI converts speech to text.
    2.  It instantly retrieves/generates **Visual Flashcards** of the signs.
    3.  The Deaf user reads the signs on the screen.

---

## 🛠️ Technical Details
* **Platform:** Google Colab (Python + JavaScript Bridge).
* **Computer Vision:** MediaPipe Hands (Google).
* **Audio Engine:** Web Speech API (Native Browser Support).
* **Database:** Dynamic Image Generation (No downloads required).

---
*Created by Muhammad Imad Aziz Khan - Sapienza University of Rome*
