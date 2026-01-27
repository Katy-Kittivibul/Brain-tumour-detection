# Brain Tumor MRI Segmentation & Detection

This project uses YOLOv8 to detect and classify brain tumors from MRI scans. It includes a training pipeline, a batch prediction script, and a production-grade FastAPI service for real-time inference.

## Features
- **Training**: Fine-tune YOLOv8 on custom MRI datasets.
- **Inference**: Batch prediction on local images.
- **API**: FastAPI service for real-time prediction.
- **Docker**: Containerized deployment capability.

## Project Structure
- `train.py`: Script to train the YOLOv8 model.
- `predict.py`: Script for batch inference on `test_pic/`.
- `app.py`: FastAPI application for serving the model.
- `inference.py`: Core inference logic.
- `config.py`: Configuration settings (paths, hyperparameters).
- `Dockerfile`: Docker build instructions.

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Katy-Kittivibul/Brain-tumour-detection.git
   cd Brain-tumour-detection
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Training
To train the model on your dataset:
```bash
python train.py
```
*Adjust hyperparameters in `config.py`.*

### Batch Prediction
To run predictions on a folder of images:
1. Place images in `test_pic/`.
2. Run:
   ```bash
   python predict.py
   ```
Results are saved to `runs/detect/predictions`.

### Web API (FastAPI)
Start the server locally:
```bash
python -m uvicorn app:app --reload
```
Visit http://127.0.0.1:8000/docs to test the API interactively.

### Docker
Build and run the container:
```bash
docker build -t brain-tumor-api .
docker run -p 8000:8000 brain-tumor-api
```
