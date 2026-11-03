
# Fruit Ripeness Classification Web App

A web application for fruit ripeness classification using a pre-trained MobileNetV2 model. Users can upload fruit images through a React interface and receive prediction results with confidence scores.

## Tech Stack

**Frontend**
- React 19
- Tailwind CSS
- Axios

**Backend**
- Python
- Flask
- Flask-CORS
- Pillow

**Deep Learning**
- PyTorch
- Torchvision
- MobileNetV2

## Project Structure

```text
ImageProcessing/
├── BE/
│   ├── server.py
│   └── predictor.py
├── FE/
│   ├── package.json
│   └── ...
├── BT/
│   ├── dataset_processed/
│   │   └── train/
│   └── output/
│       └── best_model_v2.pt
├── requirements.txt
└── README.md
```

> Note: The trained model file and processed dataset must be placed in the expected directories before running the backend.

## Prerequisites

Make sure you have installed:

- Python
- Node.js and npm
- Git

## Setup and Installation

### 1. Clone the repository

```powershell
git clone https://github.com/ChinhNguyen1105/ImageProcessing.git
cd ImageProcessing
```

### 2. Set up the Python environment

Open **PowerShell** at the project root directory.

Create a virtual environment:

```powershell
python -m venv venv
```

Activate the virtual environment:

```powershell
.\venv\Scripts\Activate.ps1
```

Install the required Python packages:

```powershell
pip install -r requirements.txt
```

## Running the Application

The backend and frontend must be started separately in two terminal windows.

### 1. Start the Backend

From the project root directory, activate the virtual environment if it is not already active, then run:

```powershell
python .\BE\server.py
```

The Flask server will run at:

```text
http://localhost:5000
```

Prediction endpoint:

```text
POST http://localhost:5000/predict
```

The endpoint accepts an image through the `image` form-data field and returns the predicted ripeness class and confidence score in JSON format.

### 2. Start the Frontend

Open another PowerShell terminal:

```powershell
cd FE
npm install
npm run dev
```

Open the application in your browser:

```text
http://localhost:5173
```

## Usage

1. Open the frontend in your browser.
2. Upload a fruit image using the upload area or drag and drop.
3. Preview the selected image.
4. Run the prediction.
5. View the predicted ripeness class and confidence score.

## Notes

- Start the Flask backend before using the frontend prediction feature.
- Ensure the trained model file `best_model_v2.pt` is available in the expected location.
- The backend uses CUDA when available; otherwise, it runs on CPU.
