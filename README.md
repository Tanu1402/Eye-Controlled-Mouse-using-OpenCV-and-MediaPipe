# Eye-Controlled-Mouse-using-OpenCV-and-MediaPipe
This project allows hands-free computer control using eye movements and blinking. It leverages OpenCV for real-time image processing, MediaPipe FaceMesh for detecting facial landmarks, and PyAutoGUI to simulate mouse movements and clicks.
👀 What does this project do?
👉 It tracks your eye movements to move the mouse cursor, and a simple blink acts as a mouse click!
💡 How does it work?
Captures Video Input 🎥 – Uses OpenCV to access your webcam.
Detects Facial Landmarks 🏷️ – MediaPipe extracts 468 facial points.
Tracks Eye Position 👁️ – Maps the eye’s position to the screen.
Moves the Cursor 🖱️ – Uses PyAutoGUI to control the mouse.
Detects Blinking 👀 – If you blink for a short moment, it clicks!
🚀 Applications:
✅ Hands-free accessibility for disabled users
✅ Futuristic interaction with devices
✅ Experimental AI-based control systems
Modules Explanation:
1️⃣ OpenCV (cv2) – Image Processing
Captures video from your webcam
Converts images to RGB format
Mirrors the video feed for natural movement
📌 Code Snippet:
frame = cv2.flip(frame, 1)  # Flip horizontally for natural movement
rgb_frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
2️⃣ MediaPipe FaceMesh – Facial Landmark Detection
Detects 468 key facial landmarks
Tracks eye position for cursor movement
Detects eye blinking for clicks
📌 Code Snippet:
face_mesh = mp.solutions.face_mesh.FaceMesh(refine_landmarks=True)
landmark_points = output.multi_face_landmarks
3️⃣ PyAutoGUI – Mouse Control
Moves the cursor based on eye movement
Clicks when blinking is detected
Works on all screen sizes
📌 Code Snippet:
pyautogui.moveTo(screen_x, screen_y)  # Move cursor
pyautogui.click()  # Simulate mouse click
4️⃣ Eye Blinking Detection
Detects the top and bottom eyelid positions
If the distance is less than 0.004, it's a blink
Simulates a mouse click
📌 Code Snippet:
if (left[0].y - left[1].y) < 0.004:  
    pyautogui.click()
