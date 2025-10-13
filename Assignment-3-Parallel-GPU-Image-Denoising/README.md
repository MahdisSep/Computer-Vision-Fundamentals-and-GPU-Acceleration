# ⚡ High-Performance Image Denoising using Parallel Computing (CUDA/PyCUDA)

## 📝 Overview
This project explores the dramatic performance benefits of **Parallel Computing** by implementing an image denoising algorithm (specifically, a **Non-Local Means Filter** or similar computationally intensive filter) on a **GPU** using the **PyCUDA** framework. The primary goal was to compare the processing time and quality metrics (SSIM, PSNR) between the CPU-based implementation and the highly optimized GPU implementation.

## 🛠️ Technologies Used
* **Language:** Python, CUDA C (embedded in Python via PyCUDA)
* **Libraries:** `PyCUDA`, `NumPy`, `OpenCV (cv2)`, `Scikit-image (skimage)` (for SSIM/PSNR calculation)
* **Hardware:** NVIDIA GPU (for execution via Colab/local setup)

## 🚀 Key Implementation Highlights

The core of this assignment is demonstrating proficiency in porting computationally intensive image processing tasks from a sequential CPU environment to a parallel GPU environment.

1.  **CUDA Kernel Development:** Wrote custom CUDA kernel code (in a string format within Python) responsible for parallel pixel-wise or patch-wise operations (e.g., applying the filter or calculating metrics).
2.  **PyCUDA Integration:** Utilized `PyCUDA` to manage the GPU workflow:
    * **Memory Transfer:** Efficiently copied image data from the host (CPU memory) to the device (GPU memory).
    * **Kernel Invocation:** Executed the custom CUDA kernels with optimized **grid and block dimensions** to maximize parallelism.
    * **Result Retrieval:** Transferred the processed image data back from the device to the host for visualization and assessment.
3.  **Performance Benchmarking:** Conducted rigorous timing experiments across different noise levels (standard deviations of 10, 20, 30) for both CPU and GPU implementations.
4.  **Quantitative Evaluation:** Assessed the output quality using industry-standard metrics:
    * **Structural Similarity Index Measure (SSIM)**
    * **Peak Signal-to-Noise Ratio (PSNR)**

## 📈 Performance Results (Example)

The results clearly showed the significant performance gain offered by GPU acceleration.

| Noise Level ($\sigma$) | CPU Time (s) | GPU Time (s) | Speedup (x) |
| :--------------------: | :----------: | :----------: | :---------: |
| 10                     | $\approx 0.95$ | $\approx 0.0002$ | $>4000\times$ |
| 20                     | $\approx 0.94$ | $\approx 0.00015$ | $>6000\times$ |
| 30                     | $\approx 0.73$ | $\approx 0.00018$ | $>4000\times$ |

> **Conclusion:** The GPU implementation provides a massive **speedup** (e.g., **$4000\times$ to $6000\times$**) compared to the CPU version for the same image quality, underscoring the necessity of parallel computing for real-time and large-scale image processing applications.

---

### **To Run This Project:**

1.  **Clone and Navigate:**
    ```bash
    git clone [Your Repository URL]
    cd Computer-Vision-Assignments/Assignment-3-Parallel-GPU-Image-Denoising
    ```
2.  **Dependencies:** This project requires `PyCUDA` and a compatible NVIDIA driver/toolkit. It's best run in an environment that supports GPU acceleration (e.g., Google Colab with a GPU runtime).
3.  **Run the Notebook:**
    Open `Cv_HW1_3 (1).ipynb` to inspect the CUDA kernel code, the PyCUDA setup, and the final benchmark results.