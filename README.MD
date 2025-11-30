# Digital Image Steganography using FFT Phase Difference 

![MATLAB](https://img.shields.io/badge/MATLAB-R2023b-orange) ![Simulink](https://img.shields.io/badge/Simulink-Model-blue) ![Status](https://img.shields.io/badge/Status-Verified-green)

It is a high-fidelity **Steganography** system developed using **MATLAB/Simulink**. It uses the **Fourier Transform Phase Difference** method to hide messages inside images without creating perceptible alterations to the original image.

---

## Project Overview

This system develops a steganographic procedure that conceals a hidden image, or **watermark**, inside another image, called the **cover** image. This innovative method differs from the conventional spatial domain steganographic procedure because, for this system, embedding is done in the **Frequency Domain**.

### Key Features
* **Steganography Approach:** Hiding data through manipulation of the frequency domain.
*   **Core Technique:** Employing **Fourier Transform Phase Difference** for embedding the watermark into the host image.
* **High Imperceptibility:** Obtains a PSNR value of **52.79 dB**, making the embedded message imperceptible to human observation.

---

## Methodology: Phase Difference

It is dependent on the property that the phase information of the Fourier transform is essential for image reconstruction.
1.  **Transformation:** Both Host and Watermark images undergo transformation to the frequency domain through the process of **2D-FFT**.
2.  **Phase Modulation:** The embedding of the watermark is done through the **Phase** component of the host image's frequency spectrum.

* *Why Phase?* Embedding via the phase spectrum, or through phase difference, can be far less noticeable than magnitude embedding.

3.  **Reconstruction:** The transformed frequency spectrum is then inverted back to a spatial domain using the Inverse FFT operation, namely, 2D-IFFT.

---

## Results

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

## 👤 Author

**Ömer Faruk Özbektaş**
[LinkedIn](https://www.linkedin.com/) | [Email](mailto:your@email.com)
