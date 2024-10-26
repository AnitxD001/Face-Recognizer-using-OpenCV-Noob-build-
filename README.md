# Facial Recognition System with OpenCV

## Overview

This project is a facial recognition system that processes an input image dataset, crops each face, and organizes the cropped faces into new folders. Using **OpenCV** for face detection and **SVM** as the primary classification algorithm, this system recognizes faces with high accuracy. 

## Features

- **Automatic face detection** and cropping from input images.
- **Organized folder structure** for each person’s cropped face images.
- **Model training** using multiple machine learning algorithms, with **SVM** chosen for its optimal accuracy.

### Dataset Structure

For the system to work effectively, organize your dataset in the following folder structure:

```plaintext
project_directory/
│
├── input_images/
│   ├── FullName/
│   │   ├── image1.jpg
│   │   ├── image2.jpg
│   │   └── ...
│   ├── FullName/
│   │   ├── image1.jpg
│   │   ├── image2.jpg
│   │   └── ...
│   └── ...
│
├── cropped_faces/             # This will be generated automatically
│   ├── FullName_PersonOne/
│   ├── FullName_PersonTwo/
│   └── ...
│
└── Face_Recogniser.ipynb
```

Each person’s images should be stored in a folder named as their **full name** (e.g., `John_Doe`). The system will automatically create a `cropped_faces` directory where each person’s cropped face images will be saved in respective folders.

### How to Run the Project

1. **Prepare the Dataset**:
   Ensure that all images are stored in `input_images`, with each person’s images in a subfolder named with their **full name** (e.g., `John_Doe`).

2. **Run the Script**:
   Execute the following command to start the face detection and cropping process:
   ```bash
   python Face_Recogniser.ipynb
   ```

3. **Face Detection and Cropping**:
   The system will detect faces in each image from `input_images`, crop out each face, and save it in a new folder under `cropped_faces`.

4. **Training the Model**:
   After cropping, the program will train a face recognition model using multiple algorithms, selecting **SVM** as the final model due to its optimal performance.

5. **Run Predictions**:
   Once trained, you can run the model on new images to predict and identify individuals based on the trained dataset.

### Important Notes

- Ensure each folder under `input_images` is named as **FullName** (e.g., `John_Doe`) for correct labeling during training.
- It is recommended to have at least **15-20 images per person** for optimal model accuracy.
  
## How It Works

1. **Face Detection**: Detects and crops faces from each image using OpenCV and dlib.
2. **Image Organization**: Crops are saved in a structured directory under `cropped_faces`, organized by each person’s full name.
3. **Feature Extraction and Training**: Extracts features from cropped faces and trains multiple classifiers, with **SVM** selected as the best-performing model for final predictions.

## Applications

- **Image Processing**: Efficiently processes non-live datasets where images are uploaded.
- **Recognition in Non-Live Systems**: Ideal for applications where real-time streaming isn’t required.

## License

This project is licensed under the MIT License. See the license file for more information.
