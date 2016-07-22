## mciantyre/scipy-opencv-notebook Docker image

All the fun of the [jupyter/scipy-notebook][jupyter-scipy-nb] Docker image, plus OpenCV 3.0.0, Python 3 bindings, and the OpenCV extra modules. Check out the [jupyter/scipy-notebook][jupyter-scipy-nb] for more information.

Note: OpenCV was built with only Python 3 bindings. Therefore, Python 2 notebooks cannot `import cv2`.

## Getting started

```
docker pull mciantyre/scipy-opencv-notebook
docker run -d -p 8888:8888 mciantyre/scipy-opencv-notebook
```

See [jupyter/scipy-notebook][jupyter-scipy-nb] for optional `run` arguments.

Navigate to `localhost:8888` in any browser, and make your first Python 3 notebook! Here's a script to find a face in a picture that you upload:

```python
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
import cv2

img = cv2.imread("your_uploaded_image.jpg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img)		# shows face without box

# If you need to find directories of data files,
# open up a terminal window from the web interface and search from there
#	find /opt -iname *haar*
face_cascade = cv2.CascadeClassifier('/opt/opencv/data/haarcascades/haarcascade_frontalface_default.xml')

faces = face_cascade.detectMultiScale(img, 1.3, 5)
for (x,y,w,h) in faces:
    cv2.rectangle(img,(x,y),(x+w,y+h),(255,0,0),2)
    roi = img[y:y+h, x:x+w]

plt.imshow(img)		# shows the face with a box around it
```

### Doesn't this exist?

In a few places! But, I wanted to make my own for practice.

Thanks to the [jupyter/docker-stacks][jupyter-stacks] project and the Jupyter team, OpenCV, and Docker. Made for the University of Pittsburgh DesignHub.

[jupyter-scipy-nb]: https://github.com/jupyter/docker-stacks/tree/master/scipy-notebook
[jupyter-stacks]: https://github.com/jupyter/docker-stacks