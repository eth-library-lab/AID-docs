## Runtime

Runtime is where the solver program runs. We have tried two different approaches:

### Locally

At the very beginning, AID asks users for a local installation of Python. Then, AID download the models and use the installed Python to run the requested solver. It is a very simple and performant approach, however it is abandoned due to the following shortcomings:

* It is hard to isolate environments. For example, the users have to install two Python binaries for running TensorFlow and PyTorch. This causes the installation process to be very complicated and error-prone.
* The users have to specify the path of the Python binary. This is not intuitive and not possible for many non-technical users.
* It is also hard for AID, as AID needs to manage the solver processes and serves as a process manager (Similar to `systemd`). It is not a good practice and out of the scope of AID project.  

### In Docker

AID now supports Docker, which is a container-based runtime. By using Docker, AID now runs different solvers in completely isolated environments, and removes the need for users to install extra software. With Docker, the AID project merely needs to download the model, encapsulate the dependencies and necessary files, build the docker image. Then Docker will manage how these images should be used and accessed. It brings the following advantages:

* The environments are completely isolated. Users can install any extra software they need without affecting other solvers.
* Users do not have to manage any processes nor manage the python environment. As long as they install Docker, they can run any solvers without any additional steps.
* For AID itself, it no longer needs to manage the solvers as processes. It can be more concentrated and more stable.