# Inverse Problem: Non-Local Means Denoising

This project implements and analyzes the Non-Local Means (NL-Means) Denoising algorithm, a powerful method for image restoration that exploits the natural redundancy of image patterns. Unlike traditional local filters that average spatially neighboring pixels, NL-Means estimates pixel values by averaging similar patches found within a search window, allowing for superior preservation of textures and edges.

The implementation utilizes the `deepinverse` library to model the inverse problem of denoising with additive Gaussian noise and `scikit-image` for the efficient execution of the NL-Means algorithm.

## Project Overview

The notebook guides you through the following steps:

1.  **Inverse Problem Definition**: Models the degradation process $v = u + n$, where $u$ is the clean image and $n$ is Gaussian noise, using `deepinverse`.
2.  **NL-Means Implementation**:
    *   Implements the algorithm described in the paper *Non-Local Means Denoising* (Buades et al., 2011).
    *   Includes a parameter selection wrapper that automatically adapts the filtering parameter $h$, patch size, and search window size based on the noise level $\sigma$.
3.  **Evaluation**:
    *   Tests the denoising performance on standard test images (e.g., Astronaut).
    *   Evaluates results using quantitative metrics: **PSNR** (Peak Signal-to-Noise Ratio) and **SSIM** (Structural Similarity Index).
    *   Provides visual comparisons and zoom-ins across multiple noise levels ($\sigma \in \{15, 30, 45\}$).

## Getting Started

### Prerequisites

Ensure you have [uv](https://github.com/astral-sh/uv) installed on your system.

### Installation

Clone the repository and sync the environment:

```bash
git clone https://github.com/mathisdrn/inverse-problem.git
cd inverse-problem
uv sync
```

### Running the Notebooks

This project uses Jupytext. You can run the Python scripts directly or use an IDE to run the notebooks.

### Building the Documentation

The project is designed to be built as a static website using MyST.

```bash
# Build the HTML site locally
uv run myst build --html
```

The site is deployed to GitHub Pages via CI/CD.

## License

This project is licensed under the MIT License (Code) and CC-BY-SA-4.0 (Content).
