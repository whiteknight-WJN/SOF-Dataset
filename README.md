# SOF-Dataset
 Synthetic Over-exposure FiveK (SOF) dataset for 2023 paper ["Raw Image Based Over-Exposure Correction Using Channel-Guidance Strategy"](https://ieeexplore.ieee.org/abstract/document/10239166)


 # Download Link
The complete Synthetic RAW Image Dataset (~94.31GB) is available via link ：https://pan.baidu.com/s/14sm4ePAr2xBf442hmjmqlA 
Extraction code：kfkg 


# RAW-based Synthetic Dataset Overview

### Purpose and Necessity
To assess the effectiveness and versatility of the proposed over-exposure correction model, and to facilitate efficient comparison between different methodologies, we identified a need for an extensive collection of RAW/sRGB images rendered with realistic over-exposure errors and corresponding accurately exposed ground truth images. As highlighted in Section 2, existing datasets lack the diversity and scale required to robustly support over-exposure correction research based on RAW data. This gap in the research landscape necessitated the creation of a new RAW-based synthetic dataset.

### Dataset Creation Methodology
Employing the over-exposure image rendering technique proposed by Afifi et al. allowed for more precise simulation of complex real-world over-exposure conditions using raw image properties. Our dataset is derived from the [MIT-Adobe FiveK dataset](https://data.csail.mit.edu/graphics/fivek/), subjected to a rigorous selection process to ensure only high-quality, representative images were included. This process led to the retention of 1,595 high-quality reference RAW images in our final dataset.

### Image Rendering and Processing
Each RAW image underwent a detailed rendering process to emulate real exposure errors. Pixel values were linearly scaled to reflect the difference in exposure time and then clipped to align with the brightness and dynamic range of the ground truth images. A sophisticated Python script, utilizing Rawpy (a Python wrapper for LibRaw), was employed to first decompose Bayer raw images from various cameras into standardized four-channel RGGB images. We then proportionally adjusted the illumination of these images to generate simulated overexposed images from the corresponding ground-truth images. The exposure ratio between the overexposed image and the ground-truth image was meticulously chosen from a set of values [3, 5, 8, 10] to render images with specific over-exposure errors. The ground truth images are the corresponding short-exposure images in a standard 8-bit sRGB space, processed through a simplified pipeline using Rawpy.

### Dataset Composition
The final synthetic dataset comprises 6,380 16-bit RAW images (convertible to sRGB space using Rawpy) with four distinct digital over-exposure settings, paired with 1,595 8-bit sRGB ground truth images. The dataset is split into two subsets: a training set consisting of 6,244 image pairs, and a testing set of 136 image pairs. Importantly, the training and testing sets do not share any common scenes, ensuring the integrity and diversity of the dataset for model training and evaluation purposes.

