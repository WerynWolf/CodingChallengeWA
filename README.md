# CodingChallengeWA
### Eryn Azalea Wolf's application to the Wisconsin Autonomous Perception team


##### LIBRARIES USED
- OpenCV / cv2 (Blob Detection, LOBF regression, image processing)
- Numpy / np (List/Tuple/Array management)
- MatPlotLib.pyplot / plt (Google Colab blocked cv2.imshow())
- os / os (Enable image to be written into Google Drive)


##### Outline of Methodology (Detailed methodology found in code comments)
- Extract image, convert to HSV (better contrast with cone surroundings)
- Filter image on Saturation and Value to remove background
- Smooth image to ease Blob Detection
- Use size-filtered Blob Detection to eliminate final unwanted regions
- Convert resultant Keypoints into usable coordinates
- Split Keypoint data into halves of the image to isolate cone lanes
- Line Of Best Fit regression to get LOBF from each lane
- Print Keypoints and LOBFs onto initial image


##### What Didn't Work
- Originally tried to get cone locations using Contour Detection [Had not yet found good image pre-processing settings; May be successful if tried now]
- Considered using a provided algorithm (SIFT) to find cones using a stock image of a short cone and a moving window to scan pieces of the input image (Did not actually attempt this)
- Lots of little trials encountered along the way
  - Finding correct format to pass data into / extract usable data from OpenCV library method formats
  - Originally tried working in other Colorspaces (RGB, LAB) [Could not get eliminate enough of the background, even with blurring]
  - Lots of tuning went into getting the Blob Scanner to work correctly


Original Image            |  Solution Output
:-------------------------:|:-------------------------:
![](https://github.com/WerynWolf/CodingChallengeWA/assets/147465688/2e5b11d0-ac09-4306-8476-b45ebf692318)  | ![](https://github.com/WerynWolf/CodingChallengeWA/assets/147465688/e60c104c-5ad5-471b-b770-5652dda2767d)
