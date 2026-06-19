# Human Activity Classification Using Pose Estimation

## Overview

This project implements a human activity recognition system using pose estimation and joint angle analysis. A pre-trained pose detection model is used to extract body keypoints from video frames, compute meaningful joint angles, and classify human activities through a rule-based approach.

## Objectives

* Detect human body keypoints using a pre-trained pose estimation model.
* Apply smoothing techniques to reduce keypoint jitter.
* Compute and analyze joint angles over time.
* Design a rule-based activity classifier.
* Evaluate classification performance against manually labeled ground truth.

## Features

### Pose Detection

* Human pose estimation using MediaPipe Pose.
* Skeleton visualization on video frames.
* Keypoint smoothing using moving average filtering.

### Joint Angle Analysis

* Knee Angle Computation
* Elbow Angle Computation
* Hip Angle Computation
* Temporal angle tracking and visualization

### Activity Classification

* Rule-based classification using joint angle thresholds.
* Detection of activity transitions.
* Frame-by-frame activity labeling.

## Activities Detected

* Standing
* Sitting
* Arm Raising

*(Activities may vary depending on the selected video source.)*

## Technologies Used

* Python
* OpenCV
* MediaPipe
* NumPy
* Matplotlib
* Jupyter Notebook

## Project Structure

```text
├── data/
│   └── input_video.mp4
├── notebooks/
│   └── activity_classification.ipynb
├── results/
│   ├── skeleton_output.mp4
│   ├── angle_plots.png
│   └── classification_results.csv
├── report/
│   └── report.pdf
├── README.md
└── requirements.txt
```

## Methodology

### 1. Pose Detection

Body landmarks are extracted from each video frame using MediaPipe Pose.

### 2. Keypoint Smoothing

A moving average filter is applied to reduce noise and jitter in detected keypoints.

### 3. Joint Angle Computation

Angles are calculated using three landmark points:

[
\theta = \cos^{-1}\left(\frac{BA \cdot BC}{|BA||BC|}\right)
]

### 4. Activity Classification

Activities are classified using predefined joint angle thresholds.

Example Rules:

* Knee Angle > 160° → Standing
* Knee Angle < 120° → Sitting
* Elbow Angle < 90° → Arm Raised

### 5. Evaluation

Predicted labels are compared with manually annotated ground truth to calculate classification accuracy.

## Results

* Skeleton visualization generated successfully.
* Joint angle variations tracked over time.
* Activity transitions identified.
* Classification accuracy calculated and reported.

## Video Source

**Video Used:** [Add your video file name or YouTube link here]

## How to Run

1. Clone the repository

```bash
git clone https://github.com/yourusername/human-activity-classification.git
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Run the notebook

```bash
jupyter notebook
```

4. Open and execute:

```text
activity_classification.ipynb
```

## Author

**Saira Jabeen**
BS Artificial Intelligence
Dawood University of Engineering & Technology

## License

This project is submitted as part of the Computer Vision course academic assignment.
