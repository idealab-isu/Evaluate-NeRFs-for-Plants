# Dataset Documentation

## Directory Structure

```
Dataset
├── Ground Truth Point Clouds And Alignment Matrices
│   ├── CCL-scanned-data-multiple-polycam-images-processed
│   ├── CCL-scanned-data-outdoor-stage2-low-height-processed
│   └── CCL-scanned-data-single-img-50-qual-90-processed
└── Images and Poses
    ├── CCL-scanned-data-multiple-polycam-images-processed
    ├── CCL-scanned-data-outdoor-stage2-low-height-processed
    ├── CCL-scanned-data-single-img-50-qual-90-processed
    ├── lpips-validation-data-processed
    ├── lpips-validation-data-processed-1
    ├── lpips-validation-data-processed-2
    ├── lpips-validation-data-processed-3
    ├── lpips-validation-data-processed-4
    └── lpips-validation-data-processed-5
```

## Overview

This dataset is structured to support research in 3D reconstruction and computer vision, particularly for plant-based scenarios. It contains two main components: captured images with their corresponding poses, and ground truth LiDAR scans for evaluation.

## Dataset Components

### 1. Images and Poses

The "Images and Poses" folder contains datasets captured using Polycam, which have been processed for use with 'nerfstudio'. Each subfolder in this directory includes:

- Original images
- Downsampled images (by factors of 2, 4, and 8)
- A 'transform.json' file containing camera pose information

### 2. Ground Truth Point Clouds And Alignment Matrices

This folder contains the corresponding LiDAR scans (.ply files) that serve as ground truth for the captured scenes. These scans are essential for evaluating the accuracy of 3D reconstructions.

## Scenario Identifiers

The dataset includes three main scenarios, each corresponding to a specific research setup:

1. **CCL-scanned-data-multiple-polycam-images-processed**: 
   - Scenario-III in the research paper
   - Represents multiple plants outdoors in a field setting

2. **CCL-scanned-data-outdoor-stage2-low-height-processed**: 
   - Scenario-II in the research paper
   - Represents multiple plants indoors

3. **CCL-scanned-data-single-img-50-qual-90-processed**: 
   - Scenario-I in the research paper
   - Represents a single plant indoors

## Additional Data

Folders prefixed with "lpips" (e.g., lpips-validation-data-processed) contain only images and poses, without corresponding ground truth data. These are typically used for additional validation or testing purposes.

## Folder Contents Example

Here's an example of what you might find in a typical scenario folder:

```
CCL-scanned-data-single-img-50-qual-90-processed
├── evaluations
├── CCL-scanned-data-single-img-50-qual-90-processed_COLMAP_SfM.log
├── CCL-scanned-data-single-img-50-qual-90-processed_trans.txt
├── CCL-scanned-data-single-img-50-qual-90-processed-cleaned-old-v1.ply
├── CCL-scanned-data-single-img-50-qual-90-processed-uncleaned.ply
├── CCL-scanned-data-single-img-50-qual-90-processed.json
└── CCL-scanned-data-single-img-50-qual-90-processed.ply
```

Key files in this structure include:

- **_trans.txt**: Contains the alignment matrix
- **.ply files**: Various versions of the LiDAR scan, including cleaned and uncleaned versions
- **.json file**: (Optional) Used for evaluation scripts based on the 'Tanks And Temples repository'

## Usage Notes

- The ground truth LiDAR scans are crucial for evaluating the accuracy of 3D reconstructions generated from the image datasets.
- When working with a specific scenario, ensure you use the corresponding images, poses, and ground truth data from the matching folders in both main directories.
- The lpips-prefixed folders can be used for additional validation but lack ground truth data.

This dataset structure allows for comprehensive research in 3D reconstruction techniques, particularly in plant-based scenarios, providing both the necessary input data (images and poses) and ground truth data for evaluation.