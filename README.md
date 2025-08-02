# face-recognition-with-YOLO
This project is a multi-step face authentication pipeline combining facial recognition, liveness detection using YOLO, and speech-based validation using ASR (Automatic Speech Recognition).
The purpose is to ensure that:

The user is the correct person (face match),

The face is real and not spoofed (liveness detection),

The user verbally repeats a sentence to prove they are physically present (ASR sentence matching).

This solution is suitable for secure identity verification use cases such as banking, KYC, and identity onboarding.

🧠 Technologies Used
OpenCV for webcam capture and image manipulation

face_recognition for facial matching

YOLOv8 (via Ultralytics) for real/fake face classification

speech_recognition for voice input and ASR

Pillow, arabic_reshaper, python-bidi for Persian text rendering on images

fuzzywuzzy for similarity comparison in ASR

🚀 Inference Pipeline
✅ Step 1: Face Match (Verification)
Capture face from webcam.

Compare with a pre-saved reference image using face encodings.

If face matches, proceed to next step.

Display Persian feedback directly on the webcam stream.

📁 Related Script: step1_face_verification.py

✅ Step 2: Liveness Detection with YOLO
Use YOLOv8 custom-trained model (best.pt) to classify face as real or fake.

Displays result on-screen.

If face is real, move to final step.

📁 Related Script: step2_yolo_liveness.py

✅ Step 3: ASR Sentence Matching
Show a sentence in Persian for the user to read aloud.

Use Google Speech Recognition to capture the voice.

Compare spoken sentence to original using fuzzy matching.

If accuracy > 90%, user is verified.

📁 Related Script: step3_speech_verification.py

📌 Notes
Model path: Make sure to place your trained YOLO model in the root directory and name it best.pt.

Font path: Persian font (BNazanin.ttf) must exist at the specified location for proper text display.

Reference image: Replace hossein.jpg with your target face image in the root directory.

Use the r key during runtime to trigger ASR listening and q to exit.
