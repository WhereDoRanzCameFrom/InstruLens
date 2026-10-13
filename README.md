# InstruLens: 3D Augmented Reality Musical Instrument Exploration Application
InstruLens is an innovative, interactive Augmented Reality (AR) mobile application designed to bridge the gap between traditional music education and modern immersive technology. Built using the Unity engine, the platform transforms static physical markers—such as specialized QR codes—into dynamic, multi-dimensional learning environments. The application aims to solve the lack of engagement in conventional music pedagogy by allowing users to visualize, interact with, and study high-fidelity 3D models of musical instruments directly in their real-world surroundings.

# *Source code utama dari projek ini disimpan di repositori privat untuk alasan keamanan dan hak cipta.*

📌 DEMO
# Work Page:
<img width="1916" height="967" alt="Work Page" src="https://github.com/user-attachments/assets/4ffb553e-8fb1-4c6c-a591-50180fe82731" />

# 3D Object:
<img width="1917" height="986" alt="3D Object" src="https://github.com/user-attachments/assets/7f836fcb-45c4-48ab-b29d-6a5115fc7b3d" />

# Home Page:
<img width="434" height="768" alt="Home Page" src="https://github.com/user-attachments/assets/e9898b0c-8e08-4d0e-821f-6d09fd87bd68" />

# Learn 1:
<img width="427" height="757" alt="Learn Page 1" src="https://github.com/user-attachments/assets/faa1caa3-5c1e-4ca5-a1cf-81bf7197bbf9" />

# Learn 2:
<img width="425" height="760" alt="Learn Page 2" src="https://github.com/user-attachments/assets/74ee402b-4378-4c56-9226-f04b129dbdfc" />

# Learn 3:
<img width="427" height="760" alt="Learn Page 3" src="https://github.com/user-attachments/assets/c2e54d90-50ed-4204-9080-2eca88cdbfbd" />

# Learn 4:
<img width="425" height="760" alt="Learn Page 4" src="https://github.com/user-attachments/assets/e3513502-894b-4fef-a07e-0d853e84bda7" />

# Scanning Page:
<img width="431" height="758" alt="Scanning Page" src="https://github.com/user-attachments/assets/c0465d07-b40d-46a7-9319-05041b377547" />

# About Page:
<img width="430" height="762" alt="About Page" src="https://github.com/user-attachments/assets/f1ec6937-7e2b-4f58-9fba-b0a1a1ce0bf6" />



## 📌 Project Overview & Problem Statement
In traditional learning environments, students and music enthusiasts often struggle to understand the complex anatomy, physical scale, and internal structures of musical instruments without having physical access to them. Buying multiple high-end instruments for a classroom is financially prohibitive, while 2D textbook diagrams fail to convey spatial proportions and spatial interaction.

**InstruLens** addresses this barrier by leveraging marker-based AR tracking. By scanning uniquely generated physical triggers, the application instantly instantiates optimized 3D assets (e.g., Bass, Drums, Guitar) with precise physical positioning. This allows learners to examine complex instrument geometries from a full 360-degree perspective, unlocking an intuitive and financially accessible form of experiential learning.

---

## ⚙️ Core Architecture & System Workflow

The project is engineered around a decoupled architecture separating the user interface (UI), the AR hardware tracking sub-system, and the contextual learning modules:

1. **The Scanning Engine (Marker-Based Tracking)**
   At the heart of the system is the `Scanning Scene`, which utilizes `ARCamera` configurations paired with advanced tracking libraries (such as AR Foundation or Vuforia Engine). The engine continuously samples raw camera frames, searching for specific grayscale contrast distribution and geometric alignments corresponding to the pre-baked marker database (stored within the local `Assets/Markers` directory).

2. **Dynamic Prefab Instantiation**
   To maintain optimal memory management and prevent runtime performance bottlenecks on mobile hardware, the 3D assets are stored as optimized `Prefabs` within the project architecture. Once a specific QR target or image marker achieves a high-confidence tracking match, the system dynamically instantiates the corresponding 3D model (e.g., the `JazzBass` model located under `Assets/3Ds/bass/`) as a child object bound to the spatial anchor of that marker.

3. **Contextual UI Layering (Canvas Sub-System)**
   The application implements an extensive Canvas system that overlays technical data, navigational controls, and interactive buttons over the live AR feed. This system acts as a responsive screen-space interface, allowing users to toggle between tracking modes, view instrument metadata, and fluidly transition between different learning environments without breaking immersion.

4. **Modular Learning Scenes (`Learn1` - `Learn4`)**
   Beyond simple visualization, the project is structured into sequential, dedicated modules. Once an instrument is recognized, the state-machine allows the user to transition into distinct sub-scenes (`Learn1` through `Learn4`). These specialized scenes isolate the specific 3D model, allowing the user to dive deeper into audio-visual breakdown, interact with specific components of the instrument's anatomy, and take guided introductory lessons.

---

## 🚀 Key Technical Features

* **High-Fidelity 3D Assets:** Real-time rendering of complex instrument meshes (including detailed texture maps, normals, and material channels) optimized for mobile deployment.
* **Marker-to-Object Spatial Mapping:** Robust image-target tracking that ensures the 3D asset remains rigidly anchored to the physical QR code regardless of rapid camera movements.
* **Decoupled Scene Management:** A clean architectural split between the `MainMenu`, active AR `Scanning` routines, informative `About` overlay overlays, and specialized learning modules.
* **Cross-Platform Readiness:** Designed and built targeting the Android ecosystem via Unity's universal build pipelines, utilizing scalable UI layouts that adapt to varying mobile aspect ratios.
