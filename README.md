# vehicle-detection
**Vehicle Detection and Tracking**

This project aims to detect and track vehicles in video streams using Histogram of Oriented Gradients (HOG) and a Multi-layer Perceptron (MLP) classifier.

**Feature Extraction with HOG**

HOG simplifies images by focusing on gradient distributions, making it useful for object detection. Testing various colour spaces showed YUV to be most effective for distinguishing vehicle features.
YUV is a colour space that separates image luminance (Y) from chrominance (U and V). This separation helps in object detection by focusing on brightness differences while reducing the impact of colour variations

**Dataset & Preprocessing**

A dataset of 8,792 vehicle and 8,968 non-vehicle images from the GTI and KITTI datasets was used. Features were scaled using Scikit-Learn’s Standard Scaler for optimal performance.

**Classifier Selection & Training**

Three classifiers were tested: Linear SVC, K-Nearest Neighbours, and MLP. MLP performed best among all, offering stable results and probability-based filtering to reduce false positives.

**Sliding Window Search**

A sliding window approach was used to scan images for vehicles. The search was limited to areas where cars are likely to appear, improving efficiency. Overlapping detections were aggregated into heatmaps to reduce false positives.



**Temporal Smoothing & Bounding Boxes**

To enhance stability, heatmaps from the last 10 frames were summed, and OpenCV’s contour detection was used to draw bounding boxes around detected vehicles.

**Results & Improvements**

The current model processes at ~6 FPS. Future improvements include optimizing search window calculations for speed and dynamically adjusting detection zones for varying environments.
