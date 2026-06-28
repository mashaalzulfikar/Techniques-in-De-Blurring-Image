# Techniques in De-Blurring Image

This repository contains the research documentation on *"Techniques in De-Blurring Image"*.

## Project Overview
In modern digital imaging, blur, caused by factors such as camera shake, motion, and noise, often degrades image quality, which can obscure important details and hinder accurate interpretation. This project explores and evaluates various de-blurring techniques to restore high-quality images and enhance their utility across fields like medical diagnostics, astronomy, and security.

## Key Techniques Explored
The research covers several foundational and advanced methods for image restoration:

* **Edge Spread Function (ESF):** This approach leverages edge information from the blurred image to estimate the Point Spread Function (PSF) and reconstruct the original image.
* **Neural Networks:** These are used to approximate the complex operations required for image restoration by learning from input-output pairs.
* **Blind Deconvolution:** An iterative method that estimates both the PSF and the original image simultaneously. The process refines these estimates through repeated iterations until convergence.
* **Richardson-Lucy Algorithm:** A well-known iterative method effective for recovering a latent image when the PSF is known. It requires careful management of iterations to mitigate ringing artifacts.

## Mathematical Formulation
The restoration process is modeled based on the degradation of an original image $f(x,y)$ through a system $h(x,y)$ (the PSF) with added noise $n(x,y)$. The resulting degraded image $g(x,y)$ is represented by the following convolution model:

$$g(x,y) = (h(x,y) * f(x,y)) + n(x,y)$$

## Performance Summary
The research compared various restoration methods based on their efficiency and Peak Signal-to-Noise Ratio (PSNR):

| Method | Type of Blur | Performance | PSNR ratio |
| :--- | :--- | :--- | :--- |
| Wiener Filter | Gaussian | Worst result | 17.05 |
| Lucy Richardson | Gaussian | Efficient | 21.06 |
| Blind Deconvolution | Gaussian & Motion | Efficient | 26.78 |
| Neural Network | Gaussian & Out-of-Focus | Very Efficient | 30.11 |
| ASDS-AR | Gaussian | Very Efficient | 31.20 |

## Research Challenges
The study identifies several limitations inherent in current restoration algorithms:
* **Computational Complexity:** Methods like blind deconvolution and Richardson-Lucy are computationally intensive, making them difficult for real-time applications.
* **Noise Sensitivity:** High levels of noise can adversely affect image quality and the accuracy of the restoration.
* **Local Minima:** The iterative nature of blind deconvolution can lead to convergence at local minima rather than the ideal solution.

## Reference
* Muthana, R., & Alshareefi, A. N. (2020, May). Techniques in de-blurring image. *Journal of Physics: Conference Series*, 1530(1), 012115.
