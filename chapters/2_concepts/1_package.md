\pagebreak
# Concepts

## Repository

### Solver

Solver is the minimal unit to solve a certain machine learning task. For example, a solver can be used for recognize text in an image. Technically, a solver is a single Python class that extends from `aid.Solver`. It implements the `__init__` function (where to load the pre-trained weights, initialize the parameters, and other necessary initialization) and `infer` function (where the class perform the inference). It can optionally implement `train` function, which will allow users to upload a training dataset and get their fine-tuned model (The training functionality is still in discussion status). With the class defined, AID will be able to recognize the model and run it.

Each solver has four different statuses.

* (Partial) Installed. The docker image of the solver is installed, but AID cannot find its corresponding code.
* (Fully) Installed. The solver is fully installed, i.e. the code and pre-trained weights have been installed on the machine.
* Ready. The solver has been built into a docker image and can start running at any time.
* Running. The solver is running and listening on a specific port.

### Package

Package is defined as a set of several solvers, their dependencies and all necessary files. It is used to encapsulate several solvers into a single entity, which can be downloaded, installed and used together. This feature is especially useful when the data science pipeline requires not only one machine learning model, but several different models. For example, an object recognition project usually contains object detection, image classification, instance segmentation and possibly other models.

A package and its content is illustrated in the following figure.

![Packages](https://i.loli.net/2020/05/06/7T3OuXoeCxS5Hsp.png)