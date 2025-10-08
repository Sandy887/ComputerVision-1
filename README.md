
# Vision-Based Vehicle Detection and Tracking System

Short demo project from the "Foundations of Computer Vision" course demonstrating classical computer-vision techniques for vehicle detection, tracking and analysis.

## Highlights
- Background subtraction and dense/sparse optical flow for motion analysis
- Lucas–Kanade sparse optical flow for tracking keypoints
- ORB feature detection + FLANN matching for re-identification
- Template matching for appearance-based tracking
- Trajectory extraction and visualization across frames
- Estimation of real-world speed from pixel motion (calibration required)
- Comparative evaluation of traditional tracking methods

## Demo
![Tracking demo](results/Trajectory_TM.jpg)

Short caption: Example of vehicle trajectory on sample video.


## Requirements
- Python 3.8+
- OpenCV (cv2)

## Qualitative evaluation (summary)

A short, qualitative comparison of the implemented approaches is available in the notebook (CapstoneProject_CHKEIR.ipynb). I evaluated each method on a set of practical indicators: stability, repeatability, handling of large/subtle motions, speed, feature density, drift and robustness to illumination/noise.

Summary:
- Feature tracking (Shi-Tomasi + LK): good for small motions, stable and fast; drifts with large motion or visually-similar nearby objects.
- Feature matching (ORB + FLANN): unreliable on this video (few keypoints / low resolution); requires stronger features (SIFT / deep features) or larger ROI.
- Template matching: accurate short-term if scale/appearance are stable; fails with scale changes and similar-looking objects.
- Background subtraction (MOG2): detects moving objects well but shows ghosting and merges nearby cars; needs parameter tuning and post-processing to separate close objects.

See the notebook for the full qualitative table, trajectories, and example outputs in the results/ folder.