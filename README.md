### mciantyre/scipy-opencv-notebook Docker image

All the fun of the [jupyter/scipy-notebook][jupyter-scipy-nb] Docker image, plus OpenCV 3.0.0, Python 3 bindings, and the OpenCV extra modules. Check out the [jupyter/scipy-notebook][jupyter-scipy-nb] for more information.

Note: OpenCV was built with only Python 3 bindings. Therefore, Python 2 notebooks cannot `import cv2`.

#### Doesn't this exist?

In a few places! But, I wanted to make my own for practice.

Thanks to the [jupyter/docker-stacks][jupyter-stacks] project, OpenCV, and Docker. Made for the University of Pittsburgh DesignHub.

[jupyter-scipy-nb]: https://github.com/jupyter/docker-stacks/tree/master/scipy-notebook
[jupyter-stacks]: https://github.com/jupyter/docker-stacks