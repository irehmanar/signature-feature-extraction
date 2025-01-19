# Signature Feature Extraction  

This repository implements a robust method for extracting features from binary signature images. It calculates centroids, transition counts, and aspect ratios within a recursive grid structure to aid in signature analysis and verification.  

## **Features and Capabilities**  

### **Core Functions**  
1. **find_centroid**:  
   - Calculates the centroid (center of mass) of black pixels in a specified region of a binary image.  
   - Returns the coordinates of the centroid or the midpoint of the region if no black pixels are found.  

2. **find_transitions**:  
   - Counts black-to-white pixel transitions in a specified rectangular region of the binary image.  
   - Useful for analyzing stroke patterns in the signature.  

3. **draw_centroid_grid**:  
   - Recursively divides the image into a 4x4 grid (64 cells).  
   - Extracts centroids, transition counts, and aspect ratios for each cell.  

4. **process_signature**:  
   - Processes a single signature image to compute features from the 4x4 grid.  
   - Outputs centroids, transitions, and aspect ratios for all cells.  

5. **process_all_signatures**:  
   - Processes multiple signature images in sequence (R001.png to R025.png).  
   - Saves the extracted features into a CSV file for further analysis.  

## **How It Works**  

### **Step-by-Step Workflow**  
1. Convert the image to grayscale and apply a binary threshold to create a binary image.  
2. Divide the image into a recursive 4x4 grid.  
3. For each cell in the final grid:
   - Calculate the centroid of black pixels.
   - Count black-to-white transitions.
   - Determine the aspect ratio (width/height).  
4. Save the extracted features in a CSV file.  

### **Extracted Features**  
- **Centroids**: x and y coordinates of black pixel clusters in each cell.  
- **Transitions**: Count of black-to-white pixel transitions in each cell.  
- **Aspect Ratios**: Ratio of cell width to height.  

## **Usage**  

### **Requirements**  
- `Pillow`: For image processing.  
- `csv`: To save extracted features.  

Install the required libraries using:  
```bash
pip install pillow
