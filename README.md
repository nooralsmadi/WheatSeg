# Instance Segmentation for Wheat heads

# Annotation Process Guide

This README outlines the detailed steps of our annotation process, used to accurately capture wheat head data. The process combines manual efforts with sophisticated automation techniques to ensure high-quality data for model training.

## Table of Contents

- [Manual Annotation (Polygon)](#manual-annotation-polygon)
- [Using Pretrained Models](#using-pretrained-models)
- [Using SAM with CVAT's Magic Tool](#using-sam-with-cvats-magic-tool)
- [Additional Methods](#additional-methods)
  - [Converting Bounding Boxes to Polygons Using SAM](#converting-bounding-boxes-to-polygons-using-sam)

## Manual Annotation (Polygon)

Initially, our process begins with meticulous manual annotation. This step involves the precise delineation of wheat heads in images, establishing a solid baseline dataset. Each wheat head is marked individually to capture accurate location and boundary information.

- **Task**: Annotate 250 images manually.

## Using Pretrained Models

To enhance the efficiency of our annotation process, we leverage pretrained models that are already knowledgeable in similar tasks. These models automate the annotation of new images by identifying and labeling wheat heads, significantly reducing manual effort.

- **Models Used**:
  - Wheat Segmentation Model
  - Smartphone FHB Detection
  - FHB Detection

## Using SAM with CVAT's Magic Tool

We integrate the SAM (Semantic Annotation Model) as an instructor within the CVAT Magic Tool. This approach focuses on improving annotation precision by highlighting essential features of wheat heads, thus facilitating faster and more accurate annotations.

## Additional Methods

### Converting Bounding Boxes to Polygons Using SAM

Understanding the transition from bounding boxes to polygons provides insight into reverse conversion. Typically, bounding boxes encapsulate the shape fully, but our process also includes converting these boxes back to more precise polygon shapes when necessary, utilizing SAM for enhanced accuracy.

---

*This guide serves to ensure consistency and high standards in our annotation workflow, contributing to the development of robust models for wheat head detection.*
## Models Overview

This section describes the models utilized in our annotation and processing pipeline, highlighting their unique functions and contributions to our project's goals.

### YOLOv8-seg

- **Type**: Semantic Segmentation
- **Description**: YOLOv8-seg extends the original YOLO (You Only Look Once) architecture to semantic segmentation, aiming to classify each pixel of the image into a specific category. This model is particularly effective for tasks where understanding the context and details of each image part is crucial.

### U-NET

- **Type**: Unsupervised Image-to-Image Translation
- **Description**: Although traditionally not aligned with segmentation tasks, U-NET excels in unsupervised image-to-image translation. Its utility in segmentation comes from its ability to adapt and learn from non-labeled imagery, potentially enhancing segmentation outcomes by leveraging spatial relations and textures.

### SAM (Spatial Attention Module)

- **Type**: Attention Mechanism
- **Description**: In segmentation tasks, SAM focuses on improving the segmentation model's precision by enhancing its attention to relevant areas within the image. This module is instrumental in refining outcomes by directing computational focus towards areas of interest, thereby improving overall segmentation accuracy.

### ONNX (Open Neural Network Exchange)

- **Type**: Model Format
- **Description**: ONNX offers a flexible and open standard for AI models. It simplifies the process of transferring models between different frameworks, enabling seamless integration and collaboration across various platforms. Supported by industry leaders like Microsoft, Facebook, and AWS, ONNX ensures our models are versatile and adaptable to changing technologies.

---

These models and technologies represent the cutting-edge tools employed in our workflow to ensure that our dataset is annotated with the highest accuracy and efficiency. Their integration reflects our commitment to leveraging advanced AI and machine learning techniques to enhance our project's output.

