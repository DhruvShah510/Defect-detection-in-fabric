Fabric Defect Detection using YOLOv8 with Iterative Transfer Learning
======================================================================

Project Description
-------------------
This project focuses on automated fabric defect detection using the YOLO (You Only Look Once) object detection framework. The primary goal is to identify four common types of fabric defects—Holes, Stains, Cuts, and Tear Cuts—through a highly optimized model training strategy combining Transfer Learning and Iterative Learning.

Dataset
-------
The dataset used is the "Fabric Defects Object Detection Dataset" from FigShare [17]. It contains annotated images representing four fabric defect classes:
- Holes
- Stains
- Cuts
- Tear Cuts

Each image is labeled appropriately, and the annotations are formatted to suit YOLO-style object detection tasks.

Preprocessing
-------------
To ensure uniformity and compatibility with YOLOv8, the following preprocessing steps were applied:
- Managing the labels file for each process
- Also mange the data.yaml file at each step as per requirement
- Dropping the labels at each stage as per iterative process

Model Training Strategy
-----------------------
A hybrid of **transfer learning** and **iterative learning** was implemented to improve model generalization and accuracy:

1. **Phase 1** – The YOLO model was first trained on a single class (Holes). This allowed the model to learn fine-grained features for that defect type.
2. **Phase 2** – Using the saved weights, the model was fine-tuned to include a second class (Stains) via transfer learning.
3. **Phase 3** – Tear Cuts were introduced, continuing the process of incremental learning.
4. **Phase 4** – A final comprehensive training iteration was done with all four defect classes, leveraging previously learned features.

Advantages of Iterative Transfer Learning
-----------------------------------------
- Improved accuracy through staged, focused learning
- Efficient reuse of learned features
- Faster convergence and reduced risk of overfitting
- Enhanced ability to detect overlapping or subtle defects

Model Architecture
------------------
YOLOv8s (the 'small' version of YOLOv8) was used for training due to its balance of speed and performance. The model uses the SiLU activation function and is an anchor-free architecture.

To learn more about YOLOv8 and its performance benefits over older YOLO versions, refer to the [Ultralytics YOLOv8 documentation](https://docs.ultralytics.com).

Usage
-----
1. Clone the repository or download the file as per need:
   
3. Prepare the dataset:
   - Place images and labels in the appropriate YOLO directory format.

4. Train the model:
  
5. Evaluate:
   Use mAP@50 and mAP@50-95 and precision metrics for model evaluation.

6. Inference:

Performance Metrics
-------------------
- Evaluation metrics used: mAP@50, mAP@50–95, precision 

License
-------
This project is for academic and research purposes. Please cite the original dataset source and model references appropriately.

Contributors
------------
- Dhruv Hemal Shah

