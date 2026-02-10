# 🌸 OmniComm: Multimodal Bi-Directional Accessibility Bridge

**A real-time AI tool bridging the communication gap between Deaf/Mute and Blind individuals.**

This project runs entirely in the browser via **Google Colab**. It uses **Computer Vision (MediaPipe)** and **Web Speech API** to translate between **Sign Language** and **Spoken English** in real-time, with a focus on true accessibility for both user groups.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1KZ8NUVOg32uhQOw2i_VY2rVdw2W68EYH?usp=sharing)

---

## 🎯 The Problem Solved
Direct communication between a Deaf/Mute person and a Blind person is incredibly difficult:
* The Deaf person signs, but the Blind person cannot see it.
* The Blind person speaks, but the Deaf person cannot hear it.

**OmniComm acts as the intelligent middle-man:**
1.  **Visual-to-Auditory (Deaf → Blind):** It watches the Deaf user's hands and **Speaks** the translation aloud for the Blind user.
2.  **Auditory-to-Visual (Blind → Deaf):** It listens to the Blind user's voice and instantly **Displays** high-contrast sign language flashcards for the Deaf user.

---

## 🌟 Key Features
* **Bi-Directional Translation:** Works seamlessly both ways (Sign-to-Speech & Speech-to-Sign).
* **Blind Accessible Mode:** Fully navigable without a mouse. Uses **Spacebar** control and **Audio Cues** ("System Ready", "Listening", "No signs found").
* **Dark Mode UI:** High-contrast, pure black interface designed for low-vision visibility and reduced eye strain.
* **Custom Sign Database:** Users can upload their own photos for specific signs (e.g., "Hello", "Love") to personalize the experience.

---

## 🚀 How to Run (Google Colab)

**Prerequisites:**
* Google Chrome (Required for Web Speech API).
* A webcam and microphone.

**Installation Steps:**
1.  **Open the Notebook:** Click the "Open in Colab" badge above.
2.  **Install Libraries:** Run the first cell:
    ```python
    !pip install mediapipe opencv-python-headless
    ```
3.  **Step 1: Upload Images (Required for Custom Signs):**
    * Run the "Upload Script" cell.
    * Select your custom sign images (e.g., `hello.jpg`, `thanks.png`, `love.jpeg`).
    * *Note: The filename must match the word (lowercase).*
4.  **Step 2: Start the Bridge:** Run the main `video_stream` code block.
5.  **Grant Permissions (CRITICAL):**
    * Click **"Allow"** for both **Camera** and **Microphone** in the browser popup.

---

## 🎮 User Guide

### 🖐️ Mode A: Sign-to-Speech (Deaf User)
* **Goal:** Communicate with a Blind person.
* **Action:** Perform a hand gesture to the camera.
* **Process:**
    1.  The AI detects the geometric sign (e.g., "HELLO").
    2.  It builds a sentence on the screen.
    3.  After a 4-second pause, it **reads the full sentence aloud** (TTS).
* **Supported Signs (Geometric Logic):**
    * `HELLO` (Open Palm)
    * `YES` (Thumbs Up)
    * `NO` (Index/Middle tap thumb)
    * `YOU` (Pointing)
    * `LOVE` (Spider-man sign)
    * `PEACE` (V Sign)
    * `OK` (Thumb touches Index)
    * `CLEAR` (Fist - erases current sentence)

### 🗣️ Mode B: Speech-to-Sign (Blind User)
* **Goal:** Communicate with a Deaf person.
* **Accessibility:** No mouse required.
* **Action:**
    1.  Wait for the audio cue: *"OmniComm Ready"*.
    2.  Press the **SPACEBAR** on your keyboard.
    3.  Speak a sentence (e.g., *"Hello my love"*).
* **Process:**
    1.  The AI converts speech to text.
    2.  It instantly pops up **High-Contrast Images** (the ones you uploaded!) on the screen.
    3.  The Deaf user reads the visual signs.

---

## 🛠️ Technical Stack
* **Language:** Python & JavaScript (Hybrid Bridge).
* **Computer Vision:** MediaPipe Hands (Google) for high-fidelity hand tracking.
* **Audio Engine:** Web Speech API (Native Browser Support) for TTS and STT.
* **Interface:** Custom HTML5/CSS3 overlay rendered directly in the Jupyter Notebook output.

---
*Created by **Muhammad Imad Aziz Khan** - Sapienza University of Rome*
