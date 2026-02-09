🌸 OmniComm: Multimodal Bi-Directional Accessibility Bridge
A real-time AI tool bridging the communication gap between Deaf/Mute and Blind individuals.

This project runs entirely in the browser via Google Colab. It uses Computer Vision (MediaPipe) and Web Speech API to translate between Sign Language and Spoken English in real-time, with a focus on true accessibility for both user groups.

🎯 The Problem Solved
Direct communication between a Deaf/Mute person and a Blind person is incredibly difficult:

The Deaf person signs, but the Blind person cannot see it.

The Blind person speaks, but the Deaf person cannot hear it.

OmniComm acts as the intelligent middle-man:

Visual-to-Auditory (Deaf → Blind): It watches the Deaf user's hands and Speaks the translation aloud for the Blind user.

Auditory-to-Visual (Blind → Deaf): It listens to the Blind user's voice and instantly Displays high-contrast sign language flashcards for the Deaf user.

🌟 Key Features
Bi-Directional Translation: Works seamlessly both ways.

Blind Accessible Mode: Fully navigable without a mouse. Uses Spacebar control and Audio Cues ("System Ready", "Listening", "No signs found").

Dark Mode UI: High-contrast interface designed for low-vision visibility and reduced eye strain.

Custom Sign Database: Users can upload their own photos for specific signs (e.g., "Hello", "Love") to personalize the experience.

🚀 How to Run (Google Colab)
Prerequisites:

Google Chrome (Required for Web Speech API).

A webcam and microphone.

Installation Steps:

Open the Notebook: Click the "Open in Colab" badge above.

Install Libraries: Run the first cell:

Python
!pip install mediapipe opencv-python-headless
Step 1: Upload Images (Optional):

Run the "Upload Script" cell.

Select your custom sign images (e.g., hello.jpg, thanks.png).

Note: If skipped, the system will just use text labels.

Step 2: Start the Bridge: Run the main video_stream code block.

Grant Permissions (CRITICAL):

Click "Allow" for both Camera and Microphone in the browser popup.

🎮 User Guide
🖐️ Mode A: Sign-to-Speech (Deaf User)
Goal: Communicate with a Blind person.

Action: Perform a hand gesture to the camera.

Process:

The AI detects the geometric sign (e.g., "HELLO").

It builds a sentence on the screen.

After a 4-second pause, it reads the full sentence aloud (TTS).

Supported Signs (Geometric Logic):

HELLO (Open Palm)

YES (Thumbs Up)

NO (Index/Middle tap thumb)

YOU (Pointing)

LOVE (Spider-man sign)

PEACE (V Sign)

OK (Thumb touches Index)

CLEAR (Fist - erases current sentence)

🗣️ Mode B: Speech-to-Sign (Blind User)
Goal: Communicate with a Deaf person.

Accessibility: No mouse required.

Action:

Wait for the audio cue: "OmniComm Ready".

Press the SPACEBAR on your keyboard.

Speak a sentence (e.g., "Hello my love").

Process:

The AI converts speech to text.

It instantly pops up High-Contrast Images of the signs on the screen.

The Deaf user reads the visual signs.

🛠️ Technical Stack
Language: Python & JavaScript (Hybrid Bridge).

Computer Vision: MediaPipe Hands (Google) for high-fidelity hand tracking.

Audio Engine: Web Speech API (Native Browser Support) for TTS and STT.

Interface: Custom HTML5/CSS3 overlay rendered directly in the Jupyter Notebook output.

Created by Muhammad Imad Aziz Khan - Sapienza University of Rome
