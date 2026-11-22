# Cloud Health Diagnostics

Medical scan classification deployed on AWS SageMaker. A first model identifies the scan type (X-ray, CT or MRI), then a type-specific CNN gives a preliminary classification.

**Context:** B.Tech Computer Science and Engineering project, VIT Vellore (Jul – Nov 2024). This is a student project, not a clinical tool.

## Team and roles

A three-person project.

- **Sowmya Sriram:** the cloud layer. Deployed the four CNN classifiers on AWS SageMaker, costed one endpoint per model against a single shared endpoint, and proposed a **single routing endpoint** that sends each scan to the right model. The team adopted it.
- [Sibi Karthik C V](https://github.com/sibi15)
- One other teammate.

## Approach

1. **Scan-type detection:** classify the input as X-ray, CT or MRI.
2. **Diagnosis models:** transfer learning with VGG16, VGG19, ResNet50 and DenseNet121, plus a baseline CNN.
3. **Deployment:** the models are hosted on SageMaker behind one routing endpoint, not one endpoint per model.

Accuracy ranged from **67% to 83%**, depending on the scan type and the model.

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

Python · TensorFlow, Keras, scikit-learn · AWS SageMaker, S3, Lambda · Pandas, NumPy, OpenCV
