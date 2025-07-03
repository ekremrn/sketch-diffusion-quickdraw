# sketch-diffusion-quickdraw

This project aims to generate sketches using Denoising Diffusion Probabilistic Models (DDPMs) with the "Quick, Draw!" dataset. Separate models were trained for the `cat`, `bus`, and `rabbit` classes, and their performance in generating successful sketches was evaluated both visually and with quantitative metrics.

## Project Goal

The primary objective of this project is to generate sketches of specific objects from scratch using a popular diffusion model, DDPM. Within this scope, the project examines how well the model learns to draw objects of varying complexity (e.g., the organic structure of a 'cat' versus the more geometric 'bus').

## Method

1.  **Dataset:** The simplified `.ndjson` files for the `cat`, `bus`, and `rabbit` classes from Google's "Quick, Draw!" dataset were used.
2.  **Data Preparation:**
    *   Data for each class was downloaded and split into 90% for training and 10% for testing.
    *   Vector-based strokes were converted into 64x64 pixel raster (bitmap) images.
3.  **Model:**
    *   A separate U-Net-based DDPM was trained for each class.
    *   The model operates on the principle of progressively adding noise to an image (the forward process) and then learning to reverse this process to reconstruct the original image from noise (the reverse process).
4.  **Training and Inference:**
    *   The models were trained using PyTorch.
    *   New sketch samples were generated with each trained model.
    *   The generation process was visualized as animated GIFs, showing the step-by-step emergence of a clear sketch from noise.
5.  **Evaluation:**
    *   The quality and diversity of the generated images were quantitatively measured using **FID (Fréchet Inception Distance)** and **KID (Kernel Inception Distance)** metrics by comparing them against real test images.
    *   The results were analyzed both visually and through a metrics summary table.
