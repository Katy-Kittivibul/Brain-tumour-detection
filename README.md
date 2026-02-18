# Brain Tumor MRI Segmentation & Detection

This project uses YOLOv8 to detect and classify brain tumors from MRI scans. It includes a training pipeline, a batch prediction script, and a production-grade FastAPI service for real-time inference.

## Features
- **Training**: Fine-tune YOLOv8 on custom MRI datasets.
- **Inference**: Batch prediction on local images.
- **API**: FastAPI service for real-time prediction.
- **Docker**: Containerized deployment capability.
- **CI/CD**: Automated linting and testing via GitHub Actions.

## Project Structure
- `src/`: Source code directory.
    - `train.py`: Script to train the YOLOv8 model.
    - `predict.py`: Script for batch inference on `test_pic/`.
    - `app.py`: FastAPI application for serving the model.
    - `inference.py`: Core inference logic.
    - `config.py`: Configuration settings (paths, hyperparameters).
    - `dataset.py`: Data preparation script.
    - `check_env.py`: Environment verification script.
- `models/`: Directory for trained model weights (`.pt` files).
- `tests/`: Unit and integration tests.
- `Dockerfile`: Docker build instructions.
- `.github/workflows/`: CI/CD pipeline configuration.

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Katy-Kittivibul/Brain-tumour-detection.git
   cd Brain-tumour-detection
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   # On Windows
   .\venv\Scripts\activate
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Training
To train the model on your dataset:
```bash
python src/train.py
```
*Adjust hyperparameters in `src/config.py`.*

### Batch Prediction
To run predictions on a folder of images:
1. Place images in `test_pic/`.
2. Run:
   ```bash
   python src/predict.py
   ```
Results are saved to `runs/detect/predictions`.

### Web API (FastAPI)
Start the server locally:
```bash
uvicorn src.app:app --reload
```
Visit http://127.0.0.1:8000/docs to test the API interactively.

### Testing & Linting
Run unit tests:
```bash
pytest
```

Check code quality:
```bash
flake8 .
```


### Troubleshooting
**CI/CD Build Failure**: If you encounter `Package 'libgl1-mesa-glx' has no installation candidate`, ensure your Dockerfile uses `libgl1` instead. This is due to the base image using a newer Debian version where the legacy package is removed.

### Docker
Build and run the container:
```bash
docker build -t brain-tumor-api .
docker run -p 8000:8000 brain-tumor-api
```
