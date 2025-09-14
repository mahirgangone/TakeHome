# TakeHome
Workflow
1. Image Loading and Preprocessing
•	Load aerial image (large.jpg)
•	Convert to grayscale using OpenCV
•	Apply CLAHE (Contrast Limited Adaptive Histogram Equalization) for contrast enhancement
•	Use bilateral filtering to smooth image while preserving edges
2. Image Segmentation Analysis
The project explores three different segmentation approaches:
Method 1: Thresholding
•	Binary thresholding with threshold value of 120-255
•	Creates binary mask for basic segmentation
Method 2: Edge Detection (Sobel)
•	Sobel edge detection in X and Y directions
•	Magnitude calculation and normalization
•	Useful for identifying texture boundaries
Method 3: K-means Clustering
•	Pixel intensity clustering (n_clusters=2)
•	Unsupervised segmentation based on intensity values
3. Manual Labeling Process
•	Display image with overlay grid for reference
•	Define training patches with specific coordinates:
o	Forest patches: (100,200, 300,400), (200,300, 500,600), (400,450, 530,600)
o	Non-forest patches: (500,600, 300,400), (500,600, 500,600)
•	Extract pixel samples from defined regions
•	Create labeled training dataset
4. Machine Learning Classification
•	Train logistic regression model (max_iter=1000)
•	Predict classifications for all pixels in the image
•	Generate classified image showing forest vs. non-forest areas
5. Results Visualization
•	Side-by-side comparison of original and classified images
•	Binary output showing white pixels for forest, black pixels for non-forest areas
•	Grid overlay for spatial reference
Key Parameters
Image Processing
•	CLAHE: clipLimit=2.0, tileGridSize=(8,8)
•	Bilateral Filter: d=9, sigmaColor=75, sigmaSpace=75
•	Threshold: Binary threshold at 120-255 range
Machine Learning
•	Logistic Regression: max_iter=1000
•	Training Patches: Manually defined rectangular regions
•	Feature Vector: Flattened pixel intensities
The system successfully demonstrates:
•	Effective preprocessing of aerial imagery
•	Comparison of different segmentation techniques
•	Manual training data collection workflow
•	Automated classification using machine learning
•	Clear visualization of classification results
