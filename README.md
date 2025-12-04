# GIF-Generator
A GIF generator just for fun (made in PYTHON)


## 🖼️ Python GIF Generator

This is a simple Python script designed to convert a sequence of static images into an animated **GIF** file using the **ImageIO** library.

---

### Key Features

* **Easy Conversion:** Combine multiple image files (like PNGs or JPEGs) into one animated GIF.
* **Customizable Speed:** Easily control the frame rate by adjusting the duration (delay) between frames.
* **Loop Control:** Set the GIF to loop infinitely or for a specific number of cycles.

---

### ⚙️ Installation

To run this script, you must have **Python** installed on your system along with the **ImageIO** library.

1.  **Install ImageIO:**
    ```bash
    pip install imageio
    ```
    This command ensures you have all necessary components, including dependencies like Pillow.

---

### 🚀 Usage

1.  **Prepare Images:** Place your sequential image files (e.g., `frame1.png`, `frame2.png`, etc.) in the same directory as the script.
2.  **Update Configuration:** Modify the `filenames` list in the script to include the names of your images in the desired order.
3.  **Run the Script:** Execute the Python file from your terminal:

    ```bash
    python gif_generator.py # or the name you chose for your file
    ```

The animated file, **`cat.gif`**, will be created in the directory.

### 💻 The Code

The core functionality is handled by the following script:

```python
import imageio.v3 as iio

# 1. List the filenames in the order they should appear in the GIF
filenames = ['nyan-cat1.png', 'nyan-cat2.png', 'nyan-cat3.png']
images = []

# 2. Read each image file into a list of frame data
for filename in filenames:
    images.append(iio.imread(filename))
  
# 3. Write the frames to an animated GIF file
# Output: 'cat.gif'
# duration: Time in milliseconds (500ms = 0.5s delay per frame)
# loop: 0 means infinite loop
iio.imwrite('cat.gif', images, duration = 500, loop = 0)
