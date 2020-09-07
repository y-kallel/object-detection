# Object Detection Model Creation and Conversion to TFlite



## How to Run

Run [this Colab Notebook](https://colab.research.google.com/drive/1vN6yP1eUQxKrG3fF9e0M1fdgfeuqKCYF?usp=sharing).

To use a custom dataset for object detection:

Require [Python 3.5+](https://www.python.org/ftp/python/3.6.4/python-3.6.4.exe) installed.
### Fork and clone this repository to your local machine.
```
https://github.com/y-kallel/object-detection
```
### Create a virtual enviornment and install required libraries
`pip3 install -r requirements.txt`


### Step 1: Annotate some images
- Save some photos with your custom object(s), ideally with `jpg` extension to `./data/raw` directory. (If your objects are simple like ones come with this repo, 20 images can be enough.)
- Resize those photo to uniformed size. e.g. `(800, 600)` with
```
python resize_images.py --raw-dir ./data/raw --save-dir ./data/images --ext jpg --target-size "(300, 300)"
```
Resized images locate in `./data/images/`
- Train/test split those files into two directories, `./data/images/train` and `./data/images/test`

- Annotate resized images with [labelImg](https://github.com/tzutalin/labelImg), generate `xml` files inside `./data/images/train` and `./data/images/test` folders. 

*Tips: use shortcuts (`w`: draw box, `d`: next file, `a`: previous file, etc.) to accelerate the annotation.*

- Commit and push your annotated images and xml files (`./data/images/train` and `./data/images/test`) to your forked repository.


### Step 2: Open [Colab notebook](https://colab.research.google.com/drive/1vN6yP1eUQxKrG3fF9e0M1fdgfeuqKCYF?usp=sharing)
- Replace the repository's url to yours and run it.

### Continue to follow the steps documented on the colab to train the custom model, create a frozen inference graph, and optionally convert it to a TFLite model to run on the edge
