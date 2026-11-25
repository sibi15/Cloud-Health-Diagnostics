# Cloud Health Diagnostics

Medical scan classification deployed on AWS SageMaker. A first model identifies the scan type (X-ray, CT or MRI), then a type-specific CNN gives a preliminary classification.

**Context:** B.Tech Computer Science and Engineering project, VIT Vellore (Jul – Nov 2024). This is a student project, not a clinical tool.

## Team and roles

A three-person project.

- **Sowmya Sriram:** the cloud layer. Deployed the models on AWS SageMaker, costed one endpoint per model against a single shared endpoint, and proposed a **single routing endpoint** that sends each scan to the right model.
- [Sibi Karthik C V](https://github.com/sibi15)
- One other teammate.

## Approach

1. **Scan-type detection:** classify the input as X-ray, CT or MRI.
2. **Diagnosis models:** transfer learning with ResNet50 (X-ray), DenseNet121 (MRI), VGG16 (CT – Kidney) and VGG19 (CT – Chest cancer).
3. **Deployment:** the models are stored in S3 and deployed on SageMaker; the scan-type result decides which diagnosis model handles the image.

Test accuracy, from `main_project_code.ipynb`:

| Model | Test accuracy |
|---|---|
| Scan type (ResNet50) | 83.8% |
| CT – Kidney (VGG16) | 83.8% |
| X-ray (ResNet50) | 66.4% |
| CT – Chest cancer (VGG19) | 51.4% |
| MRI (DenseNet121) | 37.6% |

## Repository

| File | Contents |
|---|---|
| [`main_project_code.ipynb`](main_project_code.ipynb) | data preparation, training and evaluation |
| [`aws_sagemaker_integration_code.ipynb`](aws_sagemaker_integration_code.ipynb) | SageMaker deployment and inference |
| [`requirements.txt`](requirements.txt) | Python dependencies |

## Run

```bash
pip install -r requirements.txt
jupyter notebook main_project_code.ipynb
```

The SageMaker notebook needs an AWS account with SageMaker access, and the deployed endpoints are billed while they run.

## Tech

Python · TensorFlow, Keras, scikit-learn · AWS SageMaker, S3 · Pandas, NumPy, OpenCV
