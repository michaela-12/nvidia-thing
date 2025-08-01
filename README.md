README.md

````markdown
# Final Project - Image Classification with Jetson Inference

This project uses NVIDIA Jetson's `jetson-inference` library to classify images with a pre-trained deep learning model. The script loads an image and predicts its class label using a specified model (default: `resnet-18`).

## 📄 File: `finalproject.py`

### 🔧 Requirements

- NVIDIA Jetson device (e.g., Jetson Nano, Xavier NX, TX2)
- JetPack SDK installed
- `jetson-inference` and `jetson-utils` Python modules
- Python 3

### 📥 Installation (if needed)

```bash
sudo apt-get install python3-pip
cd jetson-inference
mkdir build
cd build
cmake ../
make
sudo make install
````

Ensure Python bindings are built during installation.

---

## 🚀 Usage

```bash
python3 finalproject.py <image_filename> [--network <model_name>]
```

### 📝 Arguments

* `filename` (required): Path to the image you want to classify.
* `--network` (optional): Name of the model to use. Default is `resnet-18`.

Available models include:

* `googlenet`
* `resnet-18`
* `resnet-50`
* `alexnet`
* Others listed in `jetson-inference`

---

### ✅ Example

```bash
python3 finalproject.py images/cat.jpg --network=resnet-18
```

**Output:**

```
image is recognized as tabby cat (class #281) with 85.67% confidence
```

---

## 🧠 Model and Label Files

The script uses the following files:

* Model: `resnet18.onnx`
* Labels: `dataset/labels.txt`

Make sure these files are located in the correct paths relative to `finalproject.py`, or modify the script to reflect their actual locations.

### Parameters set in code:

```python
model="resnet18.onnx"
input_blob="input_0"
output_blob="output_0"
labels="dataset/labels.txt"
```

---

## 📂 File Structure

```
finalproject.py
resnet18.onnx
dataset/
  └── labels.txt
images/
  └── your_image.jpg
```

---

## 📌 Notes

* Use high-quality images for better accuracy.
* Confidence is displayed as a percentage (0–100%).
* Adjust the input/output blob names if you use a different ONNX model architecture.

---
