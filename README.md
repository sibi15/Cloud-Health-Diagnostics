# Cloud Health Diagnostics: AI Medical Scan Classifier
This project implements a deep learning pipeline for early-stage medical diagnosis, deployed using AWS SageMaker. It first detects the scan type (X-ray, CT, or MRI), then performs a preliminary classification using trained CNN models. The system is designed to assist medical professionals and patients by offering early insights ahead of formal diagnosis.

### Team and Roles:
A three-person project.
- **[Sowmya Sriram](https://github.com/sowmya0948)** – The cloud layer: deployed the models on AWS SageMaker, costed one endpoint per model against a single shared endpoint, and proposed a single routing endpoint that sends each scan to the right model.
- **[Sibi Karthik C V](https://github.com/sibi15)** – The models: data preparation, and training and evaluation of the scan-type classifier and the four diagnosis CNNs (VGG, ResNet, DenseNet).
- One other teammate

### Tools and Libraries:
- Python, AWS SageMaker, TensorFlow, Keras
- Deep Learning Models: CNN, DenseNet121, ResNet50, VGG16, VGG19
- Pandas, NumPy, OpenCV, Matplotlib, Seaborn

### Key Features:
- Classifies input images as X-ray, CT, or MRI before diagnosis
- Runs inference using pre-trained convolutional architectures
- Test accuracy ranges from 37.6% to 83.8% across the scan types and model variants (best: 83.8%)
- Enables early insights for quicker intervention in resource-limited settings
- Deployed on AWS SageMaker for scalable and low-latency cloud access

### Future Goals:
- Deploy GUI for interactive upload and result display
- Integrate patient history metadata for better diagnostic accuracy
- Expand dataset across more conditions and imaging modalities
- Enable API access for hospital management systems

### Outcome:
Built as a scalable, assistive diagnostic tool to support remote and urban clinics alike. The system speeds up the diagnostic process by automating early scan interpretation and reducing initial workload for radiologists.
