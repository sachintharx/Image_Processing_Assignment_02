# EC7212 – Computer Vision and Image Processing
## Take Home Assignment 2

This repository contains the implementation of two fundamental image processing algorithms:
1. **Otsu's Thresholding Algorithm** with synthetic image generation
2. **Region Growing Segmentation** algorithm

### 📋 Project Overview

This assignment demonstrates the implementation and analysis of two important image segmentation techniques:

- **Task 1**: Implementation of Otsu's automatic thresholding algorithm using a custom synthetic image with added Gaussian noise
- **Task 2**: Implementation of region growing segmentation algorithm with automatic seed point selection

### 🗂️ File Structure

```
Assignment_02/
├── Code/
│   ├── assignment_02.ipynb    # Main Jupyter notebook with implementations
│   ├── README.md             # This file
│   └── synthetic_image.png   # Generated synthetic image (after running)
├── image/                    # Directory for input images
│   └── (place your test images here)
└── results/                  # Output directory for results
```

### 🛠️ Requirements

#### Python Libraries
```python
- opencv-python (cv2)
- numpy
- matplotlib
- os (built-in)
```

#### Installation
```bash
pip install opencv-python numpy matplotlib
```

### 🚀 Usage

1. **Clone or download** the repository
2. **Navigate** to the Code directory
3. **Open** `assignment_02.ipynb` in Jupyter Notebook or VS Code
4. **Run all cells** sequentially

```bash
cd "C:\Users\Asus\Downloads\Image Processing\Assignment_02\Code"
jupyter notebook assignment_02.ipynb
```

### 📊 Task Descriptions

#### Task 1: Otsu's Algorithm Implementation

**Objective**: Implement Otsu's automatic thresholding algorithm and test it on a synthetic image

**Features**:
- Creates synthetic image with 3 distinct pixel values (50, 120, 200)
- Adds Gaussian noise (std=15) to simulate real-world conditions
- Implements Otsu's algorithm from scratch
- Automatically saves synthetic image locally
- Visualizes results with histograms and comparisons

**Key Functions**:
- `create_synthetic_image()`: Generates synthetic image with rectangle and circle objects
- `add_gaussian_noise()`: Adds controlled Gaussian noise
- `otsu_threshold()`: Complete implementation of Otsu's algorithm

#### Task 2: Region Growing Segmentation

**Objective**: Implement region growing algorithm for image segmentation

**Features**:
- Automatic seed point selection based on image content
- 8-connectivity neighborhood analysis
- Multiple threshold testing (5, 15, 25)
- Comprehensive visualization of segmentation results
- Statistical analysis of segmentation performance

**Key Functions**:
- `region_growing()`: Core region growing algorithm implementation
- `select_seed_points()`: Intelligent seed point selection
- `load_image_from_folder()`: Flexible image loading from ../image directory

### 📈 Results and Visualization

The notebook generates comprehensive visualizations including:

#### Task 1 Outputs:
- Original synthetic image
- Noisy image with Gaussian noise
- Otsu's thresholding result
- Histogram analysis with threshold visualization
- Side-by-side comparison

#### Task 2 Outputs:
- Original image with marked seed points
- Segmentation results for different thresholds
- Histogram with seed point values marked
- Segmentation overlay on original image
- Statistical analysis charts

### 🔧 Configuration Options

#### Synthetic Image Parameters:
```python
width = 300          # Image width
height = 300         # Image height
background = 50      # Background pixel value
object1 = 120        # Rectangle object value
object2 = 200        # Circle object value
noise_std = 15       # Gaussian noise standard deviation
```

#### Region Growing Parameters:
```python
thresholds = [5, 15, 25]    # Different similarity thresholds to test
connectivity = 8             # 8-connected neighborhood
```

### 📁 Input/Output

#### Input:
- **Synthetic Image**: Generated programmatically (300x300 grayscale)
- **External Images**: Place any test images in `../image/` directory
- **Supported Formats**: .jpg, .jpeg, .png, .bmp, .tiff

#### Output:
- **Saved Images**: `synthetic_image.png` in the Code directory
- **Visualizations**: Multiple plots showing algorithm results
- **Console Output**: Detailed statistics and algorithm parameters

### 🎯 Key Features

1. **Automatic Image Saving**: Synthetic images are automatically saved locally
2. **Flexible Image Loading**: Automatically detects and loads images from the image folder
3. **Comprehensive Visualization**: Multiple plots for thorough analysis
4. **Parameter Testing**: Tests multiple thresholds for region growing
5. **Statistical Analysis**: Detailed performance metrics and comparisons
6. **Robust Implementation**: Handles edge cases and different image types

### 📊 Expected Results

#### Task 1 - Otsu's Algorithm:
- Optimal threshold value around 85-135 (depending on noise)
- Clear separation of objects from background
- Histogram showing three distinct peaks

#### Task 2 - Region Growing:
- Segmentation quality varies with threshold values
- Lower thresholds: More conservative segmentation
- Higher thresholds: More aggressive segmentation
- Visual overlay showing segmented regions

### 🐛 Troubleshooting

**Common Issues**:

1. **No images in folder**: Algorithm falls back to synthetic image
2. **Import errors**: Ensure all required libraries are installed
3. **Memory issues**: Large images may require parameter adjustment
4. **Path issues**: Ensure correct relative paths for image folder

**Solutions**:
```python
# Check if image folder exists
import os
if not os.path.exists("../image"):
    os.makedirs("../image")

# Verify library installation
import cv2, numpy, matplotlib
print("All libraries imported successfully!")
```

### 👥 Author

**Course**: EC7212 – Computer Vision and Image Processing  
**Assignment**: Take Home Assignment 2  
**Implementation**: Complete implementation of Otsu's Algorithm and Region Growing Segmentation

### 📝 Notes

- All algorithms are implemented from scratch (no built-in segmentation functions used)
- Code is well-documented with detailed comments
- Results are reproducible with fixed random seed (42)
- Comprehensive error handling and fallback mechanisms included

---

**Happy Image Processing!