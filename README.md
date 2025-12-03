# Semi-Supervised Abdominal CT Segmentation

This project implements a semi-supervised learning framework for abdominal CT multi-organ segmentation using a 2D nnU-Net architecture. It leverages both labeled and unlabeled data to improve segmentation performance, making it efficient for scenarios with sparse annotations. The paper for this research, [semi_supervised_abdominal_organ_segmentation](https://github.com/KULKERJUN/Computer_vision_research/blob/main/semi_supervised_abdominal_organ_segmentation.pdf)

## Features

- **Architecture**: 2D nnU-Net with Encoder-Decoder structure.
- **Semi-Supervised Learning**: Uses Mean Teacher framework with consistency loss.
- **Deep Supervision**: Auxiliary losses at multiple decoder scales.
- **Data Augmentation**: Albumentations for robust training (flips, affine, noise, elastic transform).
- **Loss Function**: Combined Dice and Cross-Entropy loss.

## Dataset

The project uses the [AbdominalCT dataset](https://www.kaggle.com/datasets/kulkerjun/abdominalct) from Kaggle.
- **Images**: CT scans of the abdomen.
- **Masks**: Segmentation masks for 4 organs + background.

## Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/yourusername/Computer-Vision.git
    cd Computer-Vision
    ```

2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

The main script `semi_supervised_nnunet_abdominalct_segmentation.py` handles data downloading, training, and validation.

To run the training:

```bash
python semi_supervised_nnunet_abdominalct_segmentation.py
```

**Note**: The script is configured to download the dataset using `kagglehub`. Ensure you have your Kaggle credentials set up if required, or the data is accessible.

## Configuration

You can modify the `Config` class in the script to adjust parameters like:
- `epochs`
- `batch_size`
- `lr` (learning rate)
- `aug_strength` (augmentation strength)
- `use_semi` (enable/disable semi-supervised learning)

## Acknowledgements

- Dataset provided by [kulkerjun on Kaggle](https://www.kaggle.com/datasets/kulkerjun/abdominalct).
- Original code structure inspired by nnU-Net and semi-supervised learning literature.


