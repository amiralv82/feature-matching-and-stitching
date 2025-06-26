#  Feature Matching and Image Stitching using SIFT and ORB

This project demonstrates feature extraction, matching, and image stitching using **SIFT** and **ORB** algorithms with **OpenCV**. It visualizes and compares how these algorithms perform in terms of the number of keypoints detected and runtime, and ultimately uses SIFT for stitching two images into a single panoramic view.

---

##  Overview

The project is divided into the following stages:

1. **Grayscale Conversion**  
   Convert input color images to grayscale, as feature detectors work on intensity rather than color.

2. **Feature Extraction**  
   - **SIFT**: Extracts robust keypoints using scale-space extrema (DoG) and generates 128-dimensional descriptors.  
   - **ORB**: A fast, binary alternative using FAST + BRIEF.

3. **Performance Comparison**  
   - Count and display number of keypoints detected by each algorithm.  
   - Compare execution times.  
   - Visualize detected keypoints.

4. **Feature Matching**  
   - Uses **FLANN** (Fast Library for Approximate Nearest Neighbors) for fast matching of SIFT descriptors.  
   - **Lowe’s Ratio Test** is applied to filter good matches.

5. **Homography Estimation**  
   - A homography matrix is computed using **RANSAC** to align two images.  
   - Each matrix element is analyzed: scale, rotation, shear, translation, and perspective.

6. **Image Warping & Stitching**  
   - Warps the first image using the homography matrix.  
   - Stitches the warped image with the second one to create a seamless panorama.

---

##  Sample Results

###  SIFT vs ORB Keypoints

- **SIFT** detects ~20x more keypoints than **ORB**.
- However, **ORB** runs ~15x faster.
- Visualizations included.

###  Final Stitched Image

Two overlapping images are stitched together using SIFT keypoints and homography transformation.

---

##  Dependencies

- Python 3.x
- OpenCV
- NumPy
- Google Colab (for visualization via `cv2_imshow`)

Install dependencies:
```bash
pip install opencv-python numpy
```
⸻

Key Insights

	•	Use SIFT when accuracy and detail are important.
	•	Use ORB for speed and efficiency in real-time applications.

⸻

Theory Behind the Code

The project includes explanations (in Persian and English) for:

	•	DoG in SIFT
	•	Descriptor Construction
	•	Lowe’s Ratio Test
	•	FLANN Matching
	•	Homography Matrix Interpretation

⸻

 How to Run
 
	1.	Upload image1.jpg and image2.jpg.
	2.	Run the script or open it in Google Colab.
	3.	Visual output includes:
		•	Grayscale conversion
		•	Keypoint visualizations
		•	Feature matches
		•	Homography matrix
		•	Final stitched image


⸻

Acknowledgments

	•	OpenCV community
	•	Google Colab for easy experimentation
	•	Lowe et al. for SIFT
	•	Rublee et al. for ORB

⸻

Author

Amir-Abbas Alvand
Computer Science Student | Machine Learning Enthusiast
Feel free to connect on GitHub or reach out with feedback!
