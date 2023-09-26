This notebook demonstrates how to use the GroundingDINO and SAM models to perform zero-shot coin segmentation task on the public_coin_dataset dataset.

## Ideas 
Several ideas have been considered:
- Idea 1: 2D detection using YOLO-like architectures with OpenCV for contour detection -> A good idea for controlled lighting and perspective, not applicable otherwise.
- Idea 2: semantic segmentation of background/coins -> Viable option, can decrease performance with different coins and requires training.
- Idea 3: zero-shot class-agnostic architectures like GroundingDINO and SAM with prompt engineering -> No training required, may need fine-tunning but not necessary for common tasks 

Idea 3 has been implemented

## Requirements
- Folder structure: the code automatically retrieves the dataset, extracts its contents, and creates a new distribution.
- Necessary installations and imports are include in the source code
- Weights are from HuggingFace or offical repositories (automatic download)
## Instructions

To run the notebook, follow these steps:

1. Download the notebook and the public_coin_dataset dataset.
2. Open the notebook in Colab.
3. Click the **Runtime** menu and select **Change runtime type**.
4. Select the **GPU** runtime type and click **Save**.
5. Click the **Runtime** menu again and select **Run all**.

Once the notebook has finished running, you can view the segmentation results in the output cells.

## Results

The mIoU for the segmentation results on the public_coin_dataset dataset is **96.04%**.

## Improvements

As an improvement, SAM can be fine-tuned or adjusted for a softer border segmentation.

## Conclusion

This zero-shot pipeline based on 2D bounding boxes proposal + semantic + text prompt works fine for coin segmentation.