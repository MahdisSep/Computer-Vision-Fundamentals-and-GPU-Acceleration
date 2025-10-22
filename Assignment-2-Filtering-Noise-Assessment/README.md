# 🌟 Image Processing Fundamentals: Filtering, Denoising, and Quality Metrics

## 📝 Overview
This assignment focuses on implementing key image processing techniques, including handling raw pixel data, applying various spatial filters for noise reduction, and quantitatively assessing the results using standard image quality metrics.

## 🛠️ Technologies Used
* **Language:** Python
* **Libraries:** `OpenCV (cv2)`, `NumPy`, `Matplotlib`, `PIL` (for raw data handling)

## 🚀 Key Tasks and Techniques

The project is structured around three main technical areas:

### 1. Raw Data Handling and Image Reconstruction
* **Custom Parser:** Developed a function (`txt_to_image`) to parse raw pixel data from a custom text file format (`input1.txt`).
* **Image Reconstruction:** Successfully reconstructed the multi-channel color image (RGB) from the text-based pixel values into a standard NumPy array for processing with OpenCV.

### 2. Denoising and Filtering
* **Noise Application:** Simulated real-world conditions by adding different levels of Gaussian or Salt-and-Pepper noise to original images.
* **Filter Implementation:** Applied and compared the effectiveness of various spatial filters to mitigate noise, including:
    * **Gaussian Filter:** Used for smoothing and reducing high-frequency noise.
    * **Median Filter:** Highly effective for removing Salt-and-Pepper noise while preserving edges.
    * **Non-Local Means Denoising (`cv2.fastNlMeansDenoisingColored`):** Employed a state-of-the-art non-local algorithm for superior denoising performance by averaging pixels based on patch similarity across the entire image.

### 3. Quantitative Image Quality Assessment
To objectively evaluate the performance of each filter, two primary quality metrics were calculated:

* **Peak Signal-to-Noise Ratio (PSNR):** A traditional metric measuring the ratio between the maximum possible power of a signal and the power of corrupting noise. **(Higher PSNR = Better Quality)**.
* **Structural Similarity Index Measure (SSIM):** A perception-based metric that measures the structural similarity between the processed and original images, considering luminance, contrast, and structure. **(Closer to 1 = Better Quality)**.

## ✨ Results Highlights
The comprehensive comparison demonstrated that the **Non-Local Means Denoising** method achieved the highest SSIM and PSNR values across different noise levels, confirming its superiority over simple spatial filters for preserving important image structure while removing noise.

![images](https://github.com/MahdisSep/Computer-Vision-Fundamentals-and-GPU-Acceleration/blob/main/Assignment-2-Filtering-Noise-Assessment/results/results1.png)
![images](https://github.com/MahdisSep/Computer-Vision-Fundamentals-and-GPU-Acceleration/blob/main/Assignment-2-Filtering-Noise-Assessment/results/results2.png)

---

### **To Run This Project:**

1.  **Clone and Navigate:**
    ```bash
    git clone [https://github.com/MahdisSep/Computer-Vision-Fundamentals-and-GPU-Acceleration.git]
    cd Computer-Vision-Assignments/Assignment-2-Filtering-Noise-Assessment
    ```
2.  **Required Files:** Ensure the `input1.txt` file and any other raw image data are present.
3.  **Run the Notebook:**
    Open `Cv_HW1_2.ipynb` to see the filter implementations, metric calculations, and visualization of the results.