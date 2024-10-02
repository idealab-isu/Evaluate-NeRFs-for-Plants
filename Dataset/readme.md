```markdown
# Dataset Documentation

## Structure

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

This dataset is structured to support research in 3D reconstruction and image-based modeling, particularly for plant-based scenarios. It contains two main components: captured images with their corresponding poses, and ground truth LiDAR scans for evaluation.

## Images and Poses

The "Images and Poses" folder contains datasets captured using Polycam, which have been processed for use with 'nerfstudio'. Each subfolder represents a different capture scenario or validation set.

### Contents:
- Original images
- Downsampled images (by factors of 2, 4, and 8)
- Camera poses in 'transform.json' file

### Scenarios:
1. **CCL-scanned-data-multiple-polycam-images-processed**: 
   - Corresponds to Scenario-III in the research paper
   - Multiple plants outdoors in field

2. **CCL-scanned-data-outdoor-stage2-low-height-processed**: 
   - Corresponds to Scenario-II in the research paper
   - Multiple plants indoors

3. **CCL-scanned-data-single-img-50-qual-90-processed**: 
   - Corresponds to Scenario-I in the research paper
   - Single plant indoors

4. **lpips-validation-data-processed** (and its numbered variants):
   - Validation datasets
   - Contains only images and poses, no ground truth data

## Ground Truth Point Clouds And Alignment Matrices

This folder contains the ground truth LiDAR scans (.ply files) corresponding to the first three scenarios mentioned above. These scans serve as the reference for evaluating the accuracy of 3D reconstructions.

### Typical Contents of a Ground Truth Folder:

Using "CCL-scanned-data-single-img-50-qual-90-processed" as an example:

```
CCL-scanned-data-single-img-50-qual-90-processed/
├── evaluations/
├── CCL-scanned-data-single-img-50-qual-90-processed_COLMAP_SfM.log
├── CCL-scanned-data-single-img-50-qual-90-processed_trans.txt
├── CCL-scanned-data-single-img-50-qual-90-processed-cleaned-old-v1.ply
├── CCL-scanned-data-single-img-50-qual-90-processed-uncleaned.ply
├── CCL-scanned-data-single-img-50-qual-90-processed.json
└── CCL-scanned-data-single-img-50-qual-90-processed.ply
```

- **[scenario-name].ply**: The main LiDAR scan ground truth file
- **[scenario-name]_trans.txt**: Alignment matrix for the ground truth
- **[scenario-name]-uncleaned.ply**: Raw, unprocessed LiDAR scan
- **[scenario-name]-cleaned-old-v1.ply**: An earlier version of the cleaned scan
- **[scenario-name].json**: Optional crop file for evaluation scripts (based on Tanks And Temples repository)
- **[scenario-name]_COLMAP_SfM.log**: Intermediary file from evaluation process (not essential)

## Usage

1. For 3D reconstruction tasks:
   - Use the images and poses from the "Images and Poses" folder as input for your reconstruction algorithms.
   - The 'transform.json' file in each scenario folder contains the camera pose information.

2. For evaluation:
   - Compare your reconstructions against the ground truth .ply files in the "Ground Truth Point Clouds And Alignment Matrices" folder.
   - Use the alignment matrices (_trans.txt files) to ensure proper alignment between your reconstruction and the ground truth.

3. For validation:
   - The lpips-validation-data-processed folders can be used for additional testing or validation of your models, though they lack ground truth data.

## Note

The structure and contents of each folder may vary slightly. Always check the specific contents of the folder you're working with. The examples provided are representative but may not be identical across all scenarios.
```