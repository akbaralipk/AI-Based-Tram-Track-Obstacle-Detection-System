# AI-Based-Tram-Track-Obstacle-Detection-System

## Overview

This project presents an AI-based system designed to detect obstacles on tram railway tracks using computer vision and deep learning. The system analyzes front-view tram video footage, identifies track regions, detects obstacles, and generates alerts when potential hazards are detected.

The goal of the system is to enhance tram operational safety by providing automated monitoring of railway tracks.

## System Architecture

The proposed system uses a multi-model architecture consisting of three deep learning models:

### Track Segmentation Model

Identifies the tram track region within the video frame and segments it into safety zones.

#### General Obstacle Detection Model

Detects objects present on or near the tram track using a YOLO-based detection model.

#### Critical Obstacle Detection Model

A specialized YOLO model trained to detect high-risk obstacles such as stones and wheelchairs.

## Dataset Collection

The dataset used in this project was obtained from real-world tram front-view videos published by a tram pilot on YouTube.

### Steps involved in dataset preparation

Videos were downloaded using Python.

Video frames were extracted using OpenCV.

Images were annotated using CVAT.

Additional datasets were added to improve model performance.

## Annotation Process

Track regions were annotated using the CVAT annotation tool. Initially, only tram tracks were annotated to allow the segmentation model to learn track structure. Later, images containing obstacles were also annotated to improve robustness.

## Model Features
Track Segmentation

The track segmentation model identifies tram track regions and classifies them into two zones:

Yellow Zone – Warning region

Red Zone – Danger region

### Obstacle Detection

The object detection model identifies obstacles present on or near the tram track.

### Critical Object Detection

A specialized YOLO model detects critical obstacles such as stones and wheelchairs.

## Alert System

The system generates alerts based on obstacle location relative to the segmented track zones.

### Yellow zone triggers a warning alert with a low-intensity beep sound.

### Red zone triggers a danger alert with a high-intensity beep sound.

## Challenges and Solutions
### Track detection stopping at obstacles

The segmentation model initially stopped detecting tracks when obstacles appeared. This issue was solved by adding annotated images containing both tracks and obstacles.

### Difficulty detecting curved tracks

Additional curved track datasets were added to improve model generalization.

Low performance during night-time conditions

Night-time tram visuals were incorporated into the dataset to improve segmentation performance in low-light scenarios.

Critical obstacle detection accuracy

A separate YOLO model was trained specifically to detect stones and wheelchairs.

## Technologies Used

Python

OpenCV

YOLO

Deep Learning

Computer Vision

CVAT Annotation Tool

## Final Outcome

The final system successfully detects tram tracks and identifies obstacles in real time. The combination of segmentation, object detection, and alert mechanisms enables the system to operate under various real-world conditions including curved tracks, occlusions, and night-time environments.
