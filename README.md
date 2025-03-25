# Depth-Vision

# Depth Estimation using Deep Learning

## Team Members
- Sejal Dubey (22070126038)
- Kalyani Tewari (22070126051)
- Manasi Adhav (22070126063)

## Project Overview
Depth estimation is a fundamental task in computer vision, essential for 3D scene understanding in applications like autonomous driving, robotics, augmented reality (AR), and medical imaging. Traditional methods, such as stereo vision and LiDAR, are often costly and computationally expensive. Deep learning approaches, while promising, still face challenges in accuracy, generalization, and efficiency.

### Objective
This project aims to improve depth estimation using advanced deep learning techniques on the KITTI dataset. We develop and compare three different approaches:
1. **Pix2Pix GANs** for direct depth map generation.
2. **CNN-based U-Net with Pix2Pix GAN refinement** for enhanced depth accuracy.
3. **Pix2Pix GAN for stereo pair generation** to improve depth perception.

## Methodologies
### 1. Pix2Pix GANs for Depth Map Prediction
- **Input:** Monocular RGB image.
- **Architecture:** Conditional GAN (Generator + Discriminator).
- **Loss Function:** L1 loss + Adversarial loss.
- **Output:** Predicted depth map.
- **Training Details:**
  - Optimizer: Adam (LR = 0.0002).
  - Batch Size: 16.
  - Training Epochs: 100.

### 2. CNN-based U-Net Model with GAN Refinement
- **Input:** Monocular image.
- **Architecture:** U-Net for initial depth estimation, followed by GAN for refinement.
- **Loss Function:** RMSE + SSIM + Adversarial loss.
- **Training Details:**
  - U-Net trained first, GAN applied as a post-processing step.
  - Optimizer: Adam (LR = 0.0001).
  - Batch Size: 32.

### 3. Pix2Pix GANs for Stereo Pair Generation
- **Input:** Single monocular image.
- **Architecture:** Pix2Pix GAN for generating right-eye view from a monocular image.
- **Loss Function:** L1 loss + Adversarial loss.
- **Training Details:**
  - Optimizer: Adam (LR = 0.0002).
  - Batch Size: 16.
- **Post-processing:** Stereo depth estimation.

## Dataset
We use the **KITTI Optical Flow & Disparity Dataset**, which includes:
- **RGB Stereo Images:** Left & right camera views for depth estimation.
- **Disparity Maps:** Ground truth depth information.
- **Optical Flow Maps:** Motion estimation between frames.
- **Object Maps:** Semantic segmentation for scene understanding.

## Preprocessing Steps
- Image resizing and normalization.
- Data augmentation (if needed).
- Splitting into training and validation sets.

## Evaluation Metrics
- **RMSE (Root Mean Square Error)** – Measures the standard deviation of errors.
- **MAE (Mean Absolute Error)** – Captures average absolute errors.
- **SSIM (Structural Similarity Index)** – Evaluates perceptual image quality.

## Real-World Applications
- **Autonomous Driving:** Enhancing vehicle perception for safer navigation.
- **Robotics:** Improving robotic vision and spatial understanding.
- **AR/VR:** Enabling realistic depth-based interactions.
- **Medical Imaging:** Assisting in diagnostic depth analysis.

## References
- **KITTI Dataset:** [KITTI 2012/2015 Stereo Images](https://www.kaggle.com/datasets/klemenko/kitti-dataset)
- **Pix2Pix Depth Images:** [Source-Depth Image Pairs](https://www.kaggle.com/datasets/greg115/pix2pix-depth)

## How to Run the Project
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/depth-estimation.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Prepare the dataset and place it in the required directory.
4. Train the model:
   ```bash
   python train.py --model pix2pix --dataset kitti
   ```
5. Evaluate the model:
   ```bash
   python evaluate.py --model pix2pix
   ```
6. View results:
   ```bash
   python visualize.py --model pix2pix
   ```

## Contributors
- Sejal Dubey
- Kalyani Tewari
- Manasi Adhav

## License
This project is licensed under the MIT License - see the LICENSE file for details.

