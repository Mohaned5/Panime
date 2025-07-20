# Panime Dataset 🏞️🎨

Welcome to the **Panime Dataset**, a large-scale collection of high-quality, anime-style panoramic images and their corresponding multi-perspective views. This dataset is designed for various computer vision tasks, including novel view synthesis, 360° image understanding, and text-to-image generation.

The images in this dataset are AI-generated, offering a wide array of imaginative scenes, character designs, and environments in a consistent artistic style.

-----

## Dataset Details

The Panime dataset is comprised of two main components:

  * **Panoramic Images**: Approximately 2,000 unique 360° panoramic images.
      * Standard Resolution: `2048 x 1024`
      * Original High-Resolution: `8192 x 4096` (8K)
  * **Perspective Images**: For each panoramic image, there are 20 corresponding perspective views rendered from an icosahedron projection.
      * Resolution: `512 x 512`

Each image set is accompanied by rich metadata, including the generative text prompts and camera parameters for each view.

-----

## File Structure

The dataset is organized into `train`, `test`, and `val` splits. Within each split, a directory is created for each scene based on its panoramic prompt.

```
Panime/
├── train/
│   ├── A_vibrant_fantasy_marketplace.../
│   │   ├── pano/
│   │   │   └── image.png
│   │   └── images/
│   │       ├── 0.png
│   │       ├── 1.png
│   │       └── ... (up to 19.png)
│   └── ...
├── test/
│   └── ... (similar structure)
├── val/
│   └── ... (similar structure)
├── train.json
├── test.json
└── val.json
```

-----

## JSON Data Fields

The JSON files (`train.json`, `test.json`, `val.json`) contain a list of objects, where each object details one panoramic scene.

  * `pano`: The file path to the panoramic image.
  * `pano_prompt`: The original text prompt used to generate the panoramic image.
  * `images`: A list of 20 strings containing the file paths for each of the perspective views.
  * `prompts`: A list of 20 strings containing detailed, descriptive captions for each corresponding perspective view.
  * `cameras`: An object containing the camera parameters for the 20 perspective views:
      * `FoV`: An array containing a list of 20 numbers representing the Field of View (in degrees) for each perspective image.
      * `theta`: An array containing a list of 20 numbers representing the horizontal viewing angle (yaw, in degrees).
      * `phi`: An array containing a list of 20 numbers representing the vertical viewing angle (pitch, in degrees).

**Example JSON Entry:**

```json
[
  {
    "pano": "test/A_SWAT_team.../pano/image.png",
    "pano_prompt": "A SWAT team breaking through a door during a raid, weapons ready and precision in every movement",
    "images": [
      "test/A_SWAT_team.../images/0.png",
      "test/A_SWAT_team.../images/1.png",
      "..."
    ],
    "cameras": {
      "FoV": [[90, 90, 90, ...]],
      "theta": [[0, 72, 144, ...]],
      "phi": [[0, 0, 0, ...]]
    },
    "prompts": [
      "The image depicts two armed individuals in tactical gear, poised at a wooden door...",
      "The image features two characters dressed in tactical police uniforms, including helmets and masks...",
      "..."
    ]
  }
]
```

-----

## Download 💾

The dataset is available for download from Google Drive.

  * **Standard Resolution (20GB)**: Contains `2048x1024` panoramas and `512x512` perspective images.

      * **[Download Link Here]**(https://your-google-drive-link-for-standard-res](https://drive.google.com/file/d/1-6ejJcM-75NZMGWY5WqCHgHngbzFVabp/view?usp=share_link)

  * **High-Resolution (150GB)**: Contains the original `8192x4096` (8K) panoramic images only.

      * **[Download Link Here]**(https://your-google-drive-link-for-8k-res](https://drive.google.com/file/d/1JnByvxrkrAVIH8QbhC3IMzop0XE9tG8d/view?usp=share_link)

-----

## Citation

If you use the Panime dataset in your research, please consider citing it:

```bibtex
@misc{panime2025,
  author       = {Your Name/Your Team},
  title        = {The Panime Dataset},
  year         = {2025},
  publisher    = {GitHub},
  journal      = {GitHub repository},
  howpublished = {\url{https://github.com/your-username/panime-dataset}}
}
```

-----

## License

This dataset is released under the [Creative Commons BY-NC-SA 4.0 License](https://creativecommons.org/licenses/by-nc-sa/4.0/). You are free to share and adapt it for non-commercial purposes, provided you give appropriate credit.
