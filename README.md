# Neural Radiance Fields (NeRF) Implementation

## Overview

This project implements **Neural Radiance Fields (NeRF)**, a deep learning technique for novel view synthesis. The model reconstructs 3D scenes from a set of 2D images by learning a volumetric representation.

### Key Features

- **Positional Encoding**: Enhances model performance by encoding spatial information.
- **Ray Generation**: Converts image pixels into 3D camera rays.
- **MLP-Based Rendering**: Uses a deep neural network to predict RGB values and densities.
- **Dataset Handling**: Loads and preprocesses dataset from `tiny_nerf_data.npz`.

## Installation

To run this project, install the necessary dependencies:

```bash
pip install -r requirements 
```

## Usage

Run the following script to train the NeRF model:

```bash
jupyter notebook nerf.ipynb
```

## Core Components

### 1. Positional Encoding

- Uses Fourier features (`sin` and `cos`) to map positions to a higher-dimensional space.
- Helps the model capture high-frequency details in the scene.

### 2. Camera Ray Generation

- Converts image pixels into **rays** passing through the scene.
- Uses intrinsic and extrinsic camera parameters.

### 3. Rendering with a Neural Network

- Uses an **MLP** (Multi-Layer Perceptron) to predict color and density.
- Integrates **volume rendering** for realistic image generation.

## Dataset

The project uses the **Tiny NeRF Dataset**, available at:

```
http://cseweb.ucsd.edu/~viscomp/projects/LF/papers/ECCV20/nerf/tiny_nerf_data.npz
```

To load the dataset in Python:

```python
import keras
url = "http://cseweb.ucsd.edu/~viscomp/projects/LF/papers/ECCV20/nerf/tiny_nerf_data.npz"
data = keras.utils.get_file(origin=url)
```

## Results

- The model learns to render novel views of the scene.
- Output includes synthesized images and depth maps.

## Future Improvements

- **Enhancing MLP architecture** for better quality.
- **Optimizing positional encoding** for faster convergence.
- **Training on larger datasets** with high-resolution images.

## References

- Original NeRF Paper: *Mildenhall et al., 2020*.
- 3D volumetric rendering with NeRF: Aritra Roy Gosthipaty, Ritwik Raha 

---

