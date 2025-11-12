🌿 Plant Disease Detection with a Hybrid Multi-Branch AI Model

Overview

This project presents a Hybrid AI-based Plant Disease Detection System that combines Vision Transformers (ViT), EfficientNet, and a Morphometric MLP (Morphi-MLP) model.
It can detect and classify crop leaf diseases with over 99% accuracy, using both image data and IoT sensor inputs such as temperature, humidity, and soil moisture for context-aware predictions.

⸻

🧠 How It Works

The system accepts:
	•	Leaf images captured by a camera or drone.
	•	IoT-based environmental data like:
	•	Temperature and humidity (DHT sensors)
	•	Soil moisture and pH
	•	GPS location of the plant
	•	Timestamp (for monitoring over time)

The combination of image and sensor data helps improve the model’s robustness and adaptability to real-world conditions.

⸻

🧩 Model Architecture
<img width="1010" height="201" alt="Screenshot 2025-11-12 at 11 12 25 PM" src="https://github.com/user-attachments/assets/a637c26b-aba2-4960-94ef-53ee0471f2e8" />

After feature extraction, all branches are fused into a single embedding vector which passes through dense layers to predict one of 38 plant disease classes.

⸻

⚙️ Workflow
	1.	Feature Extraction: Each branch learns a different aspect of the image or sensor data.
	2.	Fusion Layer: Outputs are concatenated (1536 dimensions → 1024 → 512 → 38).
	3.	Classification Head: Predicts the disease type and confidence level.
	4.	Explainability: Grad-CAM heatmaps highlight affected regions.
	5.	Treatment Recommendation: Suggests control methods based on pathogen type.

⸻

🌤️ IoT Integration Example

A real-time field device (e.g., Raspberry Pi or Jetson Nano) can send a request like this:
<img width="715" height="264" alt="Screenshot 2025-11-12 at 11 18 18 PM" src="https://github.com/user-attachments/assets/a250687c-a298-42ac-bf49-353495e7b097" />


The system will process the image + IoT data and return a disease diagnosis, confidence score, and treatment suggestion.

⸻

🌾 Dataset

Trained and validated on the New Plant Diseases Dataset (Augmented)￼
	•	80,000+ leaf images
	•	38 disease classes
	•	Covers crops like apple, tomato, corn, grape, potato, cherry, and more

Dataset structure:

<img width="948" height="109" alt="Screenshot 2025-11-12 at 11 16 46 PM" src="https://github.com/user-attachments/assets/34ee7304-46dd-4cbc-8edb-21715538ccab" />


A smaller dataset_sample/ is included in this repo for quick testing.

⸻

🚀 Features
	•	Hybrid deep learning (ViT + EfficientNet + Morphi-MLP)
	•	Domain-specific augmentations: fog, shadow, droplet, and spectral jitter
	•	IoT-based environmental data fusion
	•	Real-time inference support (Flask or FastAPI)
	•	End-to-end explainability and pathogen mapping
	•	Scalable cloud and edge deployment options

⸻

⚡ Model Performance
<img width="952" height="305" alt="Screenshot 2025-11-12 at 11 14 03 PM" src="https://github.com/user-attachments/assets/8ab2a0f4-0b80-4527-bbb5-2c6e9331f968" />
🧰 Deployment Options
	•	Edge Mode: Lightweight ONNX/TFLite version for Raspberry Pi / Jetson Nano
	•	Cloud Mode: Flask or FastAPI REST API for multi-device access
	•	Hybrid Mode: Edge inference + Cloud logging and analytics

⸻

📊 Example Use Case

A farmer’s IoT setup collects soil and weather data while a drone captures leaf images.
The hybrid system analyzes both to:
	•	Detect early signs of infection
	•	Identify the likely pathogen
	•	Suggest real-time treatment recommendations
	•	Log trends over time for farm management

⸻

🧾 Summary

This project demonstrates a practical, explainable, and IoT-integrated AI solution for smart agriculture.
By combining deep vision and sensor intelligence, it enables early disease detection, precise diagnosis, and sustainable crop management.

⸻

📁 Repository Contents

<img width="950" height="102" alt="Screenshot 2025-11-12 at 11 17 11 PM" src="https://github.com/user-attachments/assets/cefda4c5-0fea-4978-99f8-8daa4d6aaf33" />



🧠 Future Scope
	•	Integration with Raspberry Pi for real-time monitoring
	•	Cloud dashboard for multi-farm disease tracking
	•	Multi-lingual voice alerts for farmers
	•	Reinforcement learning for adaptive diagnosis


