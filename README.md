# 🛠️ Cottonsage SoilSavvy AgroEye – Backend (Spring Boot)

This is the **Spring Boot backend service** for the full-stack AI-powered agricultural project **Cottonsage SoilSavvy AgroEye**. It acts as the bridge between the frontend UI and the trained ML model, handling image processing requests, making predictions via the model API, and returning disease info with recommendations.

---

## 🔁 Navigation – Other Parts of This Project

| Folder | Description |
|--------|-------------|
| [`../frontend/`](https://github.com/akshaykathwate/CottonSage_Frontend) | React-based UI where the user uploads images and views results |
| [`../model-api/`](https://github.com/akshaykathwate/Model) | Flask microservice serving the deep learning model (MobileNet, ResNet) |
| `backend/` | ⚙️ Spring Boot backend API – You're here! Receives images → Sends to model → Returns prediction to frontend |

---

## 🚀 Project Overview

The backend exposes a REST API endpoint that:
- Accepts uploaded images from the frontend
- Sends the image to the `model-api` Flask service
- Parses the prediction result
- Maps the result to a treatment recommendation
- Sends it back to the React frontend in JSON format

---

## 🛠️ Tech Stack

| Technology | Description |
|------------|-------------|
| **Java 17+** | Language |
| **Spring Boot** | Backend framework |
| **Spring Web** | REST APIs |
| **Jackson** | JSON serialization |
| **Maven** | Build tool |

---

## 🔌 REST API – Endpoint Details

### 📥 POST `/api/predict`

Uploads an image, performs prediction, and returns result.

#### ✅ Request:
- Method: `POST`
- Content-Type: `multipart/form-data`
- Body: FormData with `image` field

#### 🔁 Backend Processing Flow:
1. Accepts image from React frontend
2. Sends to Flask model API (`http://localhost:5000/predict`)
3. Receives disease prediction and confidence
4. Maps prediction to recommendation using logic/service
5. Returns JSON to frontend


