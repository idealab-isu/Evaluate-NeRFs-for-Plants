# Dataset Documentation

## Overview
This dataset supports research in 3D reconstruction and computer vision, focusing on plant-based scenarios. It consists of two main components:

1. Captured images with corresponding poses
2. Ground truth LiDAR scans for evaluation

## Research 
This is used in the paper : Evaluating Neural Radiance Fields for 3D Plant Geometry Reconstruction in Field Conditions 
Available Online: https://spj.science.org/doi/full/10.34133/plantphenomics.0235


## Dataset Structure

The dataset is organized into two primary folders:

1. **Images and Poses**
2. **Ground Truth Point Clouds And Alignment Matrices**

### Images and Poses

This folder contains datasets captured using Polycam, processed for use with 'nerfstudio'. Each subfolder includes:

- Original images
- Downsampled images (by factors of 2, 4, and 8)
- A 'transform.json' file containing camera pose information

### Ground Truth Point Clouds And Alignment Matrices

This folder contains the corresponding LiDAR scans (.ply files) that serve as ground truth for the captured scenes.

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

Folders prefixed with "lpips" (e.g., lpips-validation-data-processed) contain only images and poses, without corresponding ground truth data. These are used for additional validation or testing purposes.

## Detailed Directory Structure

For those interested in the complete directory structure:

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

If you find this helpful, consider citing: 
```
@article{arshad2024evaluating,
  title={Evaluating Neural Radiance Fields for 3D Plant Geometry Reconstruction in Field Conditions},
  author={Arshad, Muhammad Arbab and Jubery, Talukder and Afful, James and Jignasu, Anushrut and Balu, Aditya and Ganapathysubramanian, Baskar and Sarkar, Soumik and Krishnamurthy, Adarsh},
  journal={Plant Phenomics},
  volume={6},
  pages={0235},
  year={2024},
  publisher={AAAS}
}
```