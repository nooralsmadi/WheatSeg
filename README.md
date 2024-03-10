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

We integrate the SAM  as an instructor within the CVAT Magic Tool. This approach focuses on improving annotation precision by highlighting essential features of wheat heads, thus facilitating faster and more accurate annotations.

## Additional Methods

### Converting Bounding Boxes to Polygons Using SAM

Understanding the transition from bounding boxes to polygons provides insight into reverse conversion. Typically, bounding boxes encapsulate the shape fully, but our process also includes converting these boxes back to more precise polygon shapes when necessary, utilizing SAM for enhanced accuracy.

From Poly to BoundinBox :
Converting a polygon to a bounding box is like drawing the smallest possible rectangle around a shape so that the entire shape fits inside it. Imagine you have a piece of string laid out on the floor in the shape of any object, like a star or a heart. To convert this shape into a bounding box, you would walk around the shape and place markers at the furthest points north, south, east, and west of the shape. Then, you draw a rectangle using these markers as the corners. This rectangle is your bounding box, and it will cover the entire shape, making sure every part of your string shape is inside it.

![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/b5b48ed8-7cbf-4a90-8831-361a10098eff)

From BoundinBox to poly :
![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/6deb81b0-beb8-45b1-80fd-d0905729db12)

![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/c3deaa7d-b0f7-4a39-a0a4-b609d11981de)

---

*This guide serves to ensure consistency and high standards in our annotation workflow, contributing to the development of robust models for wheat head detection.*
## Models Overview

This section describes the models utilized in our annotation and processing pipeline, highlighting their unique functions and contributions to our project's goals.

### YOLOv8-seg

- **Type**: Semantic Segmentation
- **Description**: YOLOv8-seg extends the original YOLO (You Only Look Once) architecture to semantic segmentation, aiming to classify each pixel of the image into a specific category. This model is particularly effective for tasks where understanding the context and details of each image part is crucial.
![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/2acc2771-3521-4922-b5f4-ec9f9548201f)

![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/785889b1-cd93-4389-997a-9d18e335ba03)



### U-NET

- **Type**: Unsupervised Image-to-Image Translation
- **Description**: Although traditionally not aligned with segmentation tasks, U-NET excels in unsupervised image-to-image translation. Its utility in segmentation comes from its ability to adapt and learn from non-labeled imagery, potentially enhancing segmentation outcomes by leveraging spatial relations and textures.

![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/27546333-e580-4def-9fa5-ccec47976860)


### SAM 

- **Type**: Attention Mechanism
- **Description**: In segmentation tasks, SAM focuses on improving the segmentation model's precision by enhancing its attention to relevant areas within the image. This module is instrumental in refining outcomes by directing computational focus towards areas of interest, thereby improving overall segmentation accuracy.

![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/173171cb-a5c7-4b8b-8a65-aea95f2d2943)

![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/692800c9-ec23-408c-8046-9c930479f881)

### Summery 

![image](https://github.com/nooralsmadi/WheatSeg/assets/71272030/0c50a631-165b-43b0-ae93-aff2c7574ed1)


### ONNX (Open Neural Network Exchange)

- **Type**: Model Format
- **Description**: ONNX offers a flexible and open standard for AI models. It simplifies the process of transferring models between different frameworks, enabling seamless integration and collaboration across various platforms. Supported by industry leaders like Microsoft, Facebook, and AWS, ONNX ensures our models are versatile and adaptable to changing technologies.

---

These models and technologies represent the cutting-edge tools employed in our workflow to ensure that our dataset is annotated with the highest accuracy and efficiency. Their integration reflects our commitment to leveraging advanced AI and machine learning techniques to enhance our project's output.

