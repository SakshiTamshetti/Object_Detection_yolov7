# 🧠 YOLOv7 Object Detection in Google Colab

## 📌 Overview

Detect objects in **images and videos** using **YOLOv7** directly in **Google Colab**.  
Upload your files, run detection, and view results — all in one simple workflow.

---

## ⚙️ Requirements

* Google Colab  
* GPU runtime (for faster detection)  
* Internet connection  

**Enable GPU:**  
`Runtime → Change runtime type → Hardware accelerator → GPU`

---

## 🪶 Setup and Execution

### 🧩 Create and Open Directory

```python
%cd /content/drive/MyDrive
!mkdir -p The_new_dir
%cd The_new_dir
```

### 📦 Clone YOLOv7 Repository

```python
!git clone https://github.com/WongKinYiu/yolov7.git
%cd yolov7
```

### 🔽 Download Pretrained Weights

```python
!wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt
```

### 🧠 Fix PyTorch Load Issue

```python
!sed -i 's/ckpt = torch.load(w, map_location=map_location)/ckpt = torch.load(w, map_location=map_location, weights_only=False)/g' models/experimental.py
```

---

## 📤 Upload Supported Files

You can upload the following **file formats** for detection:  

📁 **Supported Formats:**  
- **Images:** `.jpg`, `.jpeg`, `.png`  
- **Videos:** `.mp4`, `.avi`, `.mov`, `.mkv`  

✅ Upload any of these file types to run YOLOv7 detection and view results instantly.

---

## 🎯 Run Object Detection

### For Image

```python
!python detect.py --weights yolov7.pt --conf 0.5 --img-size 640 --source "your_image.jpg"
```

### For Video

```python
!python detect.py --weights yolov7.pt --conf 0.5 --img-size 640 --source "your_video.mp4"
```

---

## 📂 Example Output

**Input:** `cat.jpg`  
**Output:** `runs/detect/exp/cat.jpg` *(with labeled detections)*

---

## 💡 Tip

Adjust confidence or image size for better accuracy:

```python
!python detect.py --weights yolov7.pt --conf 0.3 --img-size 720 --source "your_image.jpg"
```

---

## 📜 License

YOLOv7 © [WongKinYiu](https://github.com/WongKinYiu/yolov7)  
For educational and research use only.
