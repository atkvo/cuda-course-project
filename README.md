# CMPE 297-08 - CUDA Course
## Group 5

James Grantham
Andrew Vo

## Requirements

* OpenCV 3.1
* Negative image set
    - https://drive.google.com/open?id=0ByzbnBSugN4fQk1UaXFMVFBXY3M

### Training Steps

All steps unless otherwise stated will be performed in the `trainer` folder

1. Fill the `neg_images` folder with all the negative images
2. Fill the `pos_images` folder with the cropped positives images you want to use to generate the positive images to train
3. Edit the `Makefile` (in the trainer folder) variables: 
    * POS/NEG_COUNT (to the total number of positive images to generate/negatives avail)
    * POS/NEG_USE (how many positives and negative images to train with)
4. Preparing the generating the images and image information
    * `make gen_neg_info` (creates the `negatives.info` file)
    * `make gen_pos` (superimposes the `pos_images` onto random negative images to create positive images to use for training)
5. Create the samples vector file 
    * `make create_samples` (creates the `samples.vec` file)
6. Training the cascade 
    * `make train_cascade`

### Detector Program

1. Run the Makefile in the “detector” folder  to generate the detector program
2. Navigate to the root folder in your shell (where this `README.md` is) and edit the `Makefile`
    * `cd ..`
3. Edit `Makefile` variables in the main directory
    * `CROSS_CASCADE="classifier_crosssign/cascade.xml"`
    * `STOP_CASCADE="classifier_stopsign/cascade.xml"` 
    * `CAM_INDEX=0` <- Index of your camera
6. Run `make run_detector` to run the detector program with your trained classifier
