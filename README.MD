# Digital Image Steganography using FFT Phase Difference 🔐

![MATLAB](https://img.shields.io/badge/MATLAB-R2023b-orange) ![Simulink](https://img.shields.io/badge/Simulink-Model-blue) ![Status](https://img.shields.io/badge/Status-Verified-green)

A high-fidelity **Steganography** system implemented in **MATLAB/Simulink**. This project utilizes the **Fourier Transform Phase Difference** technique to securely embed hidden information into digital images without visible distortion.

---

## 🚀 Project Overview

This project implements a steganographic algorithm that hides a secret image (watermark) within a cover image. Unlike traditional spatial domain methods, this approach operates in the **Frequency Domain**, leveraging the phase information of the FFT coefficients for robust data embedding.

### Key Features
* **Steganography Approach:** Securely hides data using frequency domain manipulation.
* **Core Technique:** Uses **Fourier Transform Phase Difference** to modulate the watermark into the host image.
* **High Imperceptibility:** Achieves a PSNR of **52.4 dB**, making the hidden data visually undetectable to the human eye.
* **Color Preservation:** Operates on the **Y (Luminance)** channel of the YCbCr color space to maintain color fidelity.

---

## 🧠 Methodology: Phase Difference

The algorithm relies on the property that phase information in the Fourier transform is crucial for image reconstruction.

1.  **Transformation:** Both the Host and Watermark images are converted to the frequency domain using **2D-FFT**.
2.  **Phase Modulation:** The watermark is embedded by modifying the **Phase** component of the host image's frequency spectrum.
    * *Why Phase?* Embedding in the phase spectrum (using phase difference) is often more robust and less perceptible than magnitude modification.
3.  **Reconstruction:** The modified frequency spectrum is converted back to the spatial domain using Inverse FFT (**2D-IFFT**).

---

## 📊 Results

The system was tested with a gain factor of **$K = 0.01$**.

| Metric | Value | Result |
| :--- | :--- | :--- |
| **PSNR** | **52.4 dB** | **Excellent.** No visible artifacts or distortion. |
| **Visual Quality** | High | The stego-image is indistinguishable from the original. |

### Visual Comparison
| Host Image | Stego-Image (Output) | Extracted Secret |
| :---: | :---: | :---: |
| ![Original](media/original_host.png) | ![Stego](media/watermarked_output.png) | ![Secret](media/extracted_watermark.png) |

---

## 🛠️ Simulation Model

The project is built using modular Simulink blocks for signal processing.

![Simulink Diagram](media/simulink_diagram.png)

* **Embedding Stage:** FFT $\to$ Phase Modification $\to$ IFFT.
* **Extraction Stage:** Difference Calculation $\to$ Phase Demodulation.

---

## 🚀 How to Run

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/yourusername/Steganography-FFT-Phase.git](https://github.com/yourusername/Steganography-FFT-Phase.git)
    ```
2.  **Open in MATLAB:**
    Open the `Steganography_FFT.slx` file.
3.  **Run Simulation:**
    Run the model to see the embedding and extraction process in real-time video viewers.

---

## 👤 Author

**[Adın Soyadın]**
*Electronics Engineering Student*

[LinkedIn](https://www.linkedin.com/) | [Email](mailto:your@email.com)

---

## ⚖️ License

Distributed under the MIT License.
