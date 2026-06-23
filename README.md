# ⚽ Football Image Dataset

A manually annotated object-detection dataset of **football (soccer) match frames**, labelled in **YOLO format** with three classes: **ball**, **player** and **referee**.

<p align="left">
  <img src="https://img.shields.io/badge/images-612-blue" alt="images">
  <img src="https://img.shields.io/badge/annotations-10%2C136-green" alt="annotations">
  <img src="https://img.shields.io/badge/classes-3-orange" alt="classes">
  <img src="https://img.shields.io/badge/format-YOLO-red" alt="format">
  <img src="https://img.shields.io/badge/license-CC--BY--4.0-lightgrey" alt="license">
</p>

---

## 📋 Overview

This dataset contains **612 images** (Full HD, 1920×1080) extracted from football match footage, each one **manually annotated** with bounding boxes. It is ready to train modern object detectors such as the [Ultralytics YOLO](https://docs.ultralytics.com/) family.

| Class id | Name      | Description                          |
|:--------:|-----------|--------------------------------------|
| `0`      | `ball`    | The match ball                       |
| `1`      | `player`  | Outfield players and goalkeepers     |
| `2`      | `referee` | Referee and assistant referees       |

## 📊 Dataset statistics

| Split     | Images | `ball` | `player` | `referee` | Total boxes |
|-----------|:------:|:------:|:--------:|:---------:|:-----------:|
| **train** |   512  |   417  |   7,278  |    634    |    8,329    |
| **val**   |   100  |    83  |   1,566  |    158    |    1,807    |
| **Total** | **612**| **500**| **8,844**|  **792**  |  **10,136** |

> The dataset is split into an 84 / 16 train–validation partition (512 / 100 images).
> One training image is a *background* sample (no objects), which is intentional and helps reduce false positives.

## 📁 Repository structure

```
football-image-dataset/
├── images/
│   ├── train/        # 512 .jpg frames
│   └── val/          # 100 .jpg frames
├── labels/
│   ├── train/        # 512 .txt YOLO annotations
│   └── val/          # 100 .txt YOLO annotations
├── data.yaml         # Ultralytics dataset configuration
├── LICENSE           # CC BY 4.0
└── README.md
```

## 🏷️ Annotation format

Labels follow the **YOLO** convention: one `.txt` file per image, with the same
base name. Each line describes one bounding box:

```
<class_id> <x_center> <y_center> <width> <height>
```

All coordinates are **normalised** to `[0, 1]` relative to the image
dimensions. Example (`labels/train/<name>.txt`):

```
1 0.387760 0.541667 0.027604 0.105556   # player
2 0.353385 0.535648 0.019271 0.108333   # referee
0 0.294531 0.541667 0.006771 0.011111   # ball
```

## 📜 License

Released under the **[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE)**
license. You are free to use, share and adapt the dataset — including
commercially — as long as you give appropriate credit.

## 📣 Citation

If you use this dataset in your work, please cite it:

```bibtex
@misc{football_image_dataset,
  title        = {Football Image Dataset: YOLO-annotated ball, player and referee detection},
  author       = {skaczylo},
  year         = {2026},
  howpublished = {\url{https://github.com/skaczylo/football-image-dataset}}
}
```

## ⭐ Support

If you find this dataset useful, please consider giving it a **star** on
GitHub — it helps others discover the project and is greatly appreciated!

---

<sub><b>Keywords:</b> football dataset · soccer dataset · YOLO dataset · object detection ·
ball detection · player detection · referee detection · sports analytics ·
computer vision · annotated images · bounding boxes · YOLOv8 · YOLO11 ·
Ultralytics · deep learning · machine learning · image dataset · training data</sub>
