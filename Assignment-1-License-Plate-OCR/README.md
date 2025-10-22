# 🏷️ Automatic License Plate Recognition (ALPR) using Classical Computer Vision

## 📝 Overview
This project implements a pipeline for **Automatic License Plate Recognition (ALPR)** using fundamental image processing techniques and the Tesseract Optical Character Recognition (OCR) engine. The goal was to accurately extract the alphanumeric text from a car's license plate in an image, focusing on robustness against noise and varying image conditions.

## 🛠️ Technologies Used
* **Language:** Python
* **Libraries:** `OpenCV (cv2)`, `pytesseract` (Tesseract Wrapper), `NumPy`

## 🚀 Key Steps in the Pipeline

The recognition process is broken down into the following sequential steps, as documented in the provided Jupyter Notebook (`Cv_HW1_1.ipynb`):

1.  **Denoising (Noise Reduction):** Utilizing filters (e.g., `FastNlMeansDenoising`) to remove unwanted noise and improve image clarity before processing.
2.  **Grayscale Conversion:** Converting the color image to grayscale for simplification.
3.  **Plate Isolation (Cropping):** Manually defining an approximate region of interest (ROI) to isolate the license plate area.
4.  **Resizing and Enhancement:** Resizing the cropped plate to a larger dimension (e.g., $2 \times$) to aid the OCR engine in clearer text detection.
5.  **Morphological Operations:** Applying operations like `MORPH_CLOSE` to connect separated text segments, fill small holes, and solidify the text features.
6.  **Thresholding (Binarization):** Using **Otsu's Binarization** (`THRESH_BINARY + THRESH_OTSU`) to automatically create a clear black-and-white image, separating text from the background optimally.
7.  **OCR Execution:** Running the `pytesseract` engine on the processed binary image, configured specifically for recognizing digits and uppercase letters common on license plates.

## 💡 Results and Conclusion

The pipeline successfully demonstrates the effectiveness of classical image processing in preparing an image for accurate OCR. The use of adaptive thresholding and morphological closing proved critical in ensuring that the Tesseract engine could reliably extract the text, even from images with moderate noise.

![images](https://github.com/MahdisSep/Computer-Vision-Fundamentals-and-GPU-Acceleration/blob/main/Assignment-1-License-Plate-OCR/results/car.jpg)
![images](https://github.com/MahdisSep/Computer-Vision-Fundamentals-and-GPU-Acceleration/blob/main/Assignment-1-License-Plate-OCR/results/results1.png)

-----

---

### **To Run This Project:**

1.  **Clone the Repository:**
    ```bash
    git clone [Your Repository URL]
    cd Computer-Vision-Assignments/Assignment-1-License-Plate-OCR
    ```
2.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    # Ensure Tesseract OCR is also installed on your system
    ```
3.  **Run the Notebook:**
    Open `Cv_HW1_1.ipynb` in Jupyter or Google Colab to see the full code and execution flow.