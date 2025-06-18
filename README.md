# Cloud-Health-Diagnostics
This project implements a deep learning pipeline for early-stage medical diagnosis, deployed using AWS SageMaker. It first detects the scan type (X-ray, CT, MRI), then performs a preliminary classification using trained CNN models. The system is built to assist medical professionals and patients by offering early insights ahead of formal diagnosis.

Tools and Libraries:
- Python, TensorFlow, Keras
- Deep Learning Models: CNN, DenseNet121, ResNet50, VGG16, VGG19
- Pandas, NumPy, OpenCV, Matplotlib, Seaborn

Key Features:
- Classifies input images as X-ray, CT, or MRI before diagnosis
- Runs inference using pre-trained convolutional architectures
- Achieves 67–83% accuracy across different image types and model variants
- Enables early insights for quicker intervention in resource-limited settings
- Deployed on AWS SageMaker for scalable and low-latency cloud access

Future Goals:
- Deploy GUI for interactive upload and result display
- Integrate patient history metadata for better diagnostic accuracy
- Expand dataset across more conditions and imaging modalities
- Enable API access for hospital management systems

Outcome:
Built as a scalable, assistive diagnostic tool to support remote and urban clinics alike. The system speeds up the diagnostic process by automating early scan interpretation and reducing initial workload for radiologists.
