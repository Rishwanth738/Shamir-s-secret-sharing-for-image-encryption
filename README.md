# Shamir-s-secret-sharing-for-image-encryption
Shamir’s Secret Sharing for Image Encryption
Overview
This project implements Shamir’s Secret Sharing (SSS) to encrypt and reconstruct images. Each pixel in the grayscale image is split into multiple shares using polynomial-based encryption. A predefined number of shares (threshold) is required to reconstruct the original image.

Features
Converts an image to grayscale.

Splits each pixel into n shares using Shamir’s Secret Sharing.

Requires t shares (t < n) to reconstruct the image.

Uses Dynamic Programming to optimize polynomial evaluation.

Secure encryption using modular arithmetic.

How It Works
Image Preprocessing

Convert the image to grayscale.

Flatten it into a 1D array for pixel-wise processing.

Share Generation

Each pixel value is treated as a secret.

A random polynomial of degree t-1 is generated with the pixel as a constant term.

The polynomial is evaluated at n different x values to generate shares.

Reconstruction

Using t shares, Lagrange Interpolation is applied to retrieve the original pixel values.

The recovered pixel values are reshaped back into the original image size.

Dependencies
Python 3.x

NumPy

Matplotlib

Usage
Install dependencies:

bash
Copy
Edit
pip install numpy matplotlib
Run the script:

bash
Copy
Edit
python main.py
The script will:

Display the original grayscale image.

Generate and show an encrypted share.

Reconstruct and display the final decrypted image.

Example Output
yaml
Copy
Edit
Original Secret: <Pixel Values>
Shares: [(x1, y1), (x2, y2), ...]
Combining shares...
Reconstructed Secret: <Pixel Values>

Notes
The FIELD_SIZE is set to 257 to ensure modular arithmetic.

This implementation supports (t, n) threshold schemes, where at least t out of n shares are required to reconstruct the image.

Increasing n adds redundancy, making it more fault-tolerant.

Future Improvements
Extend support for colored images (RGB).

Implement multi-level encryption for additional security.

Optimize memory usage for high-resolution images.

