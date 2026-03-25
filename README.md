# VecToYOLO: Geospatial Training Data Generator
VecToYOLO is a powerful QGIS plugin designed to streamline the creation of deep learning datasets. It automates the process of converting large-scale satellite imagery or drone orthomosaics into localized image "chips" (patches) with corresponding label files, formatted specifically for the YOLO (You Only Look Once) object detection and segmentation framework.

## Core Features
- Dual Task Support: Supports both Object Detection (bounding boxes) and Instance Segmentation (polygon-to-mask conversion).
- Flexible Data Handling: * 8-bit Drone Orthomosaics: Standard RGB processing.
  - 16-bit Satellite Imagery: Automatic reflectance scaling (e.g., Sentinel-2 L2A) to 8-bit PNG for model compatibility.
- Advanced Data Splitting: Choose between Random splitting or Spatial splitting (using geographic rows) to ensure more robust validation and prevent data leakage.
- Customizable Overlap: Control the overlap percentage between chips—crucial for small object detection or continuous landcover mapping.
- Ready-to-Train Output: Generates a structured directory with train/ and val/ folders, a classes.txt file, and a pre-configured data.yaml file tailored for Kaggle, Google Colab, or Local environments.

## How it Works
1. Alignment: Automatically reprojects your vector annotations to match the CRS of your raster.
2. Tiling: Iterates through your specified map extent, creating image tiles based on your desired chip size and overlap.
3. Label Mapping: Maps vector attributes to class IDs and converts geographic coordinates into the normalized YOLO format.
