\pagebreak
# User Guide

## Installation

AID relies on several dependencies to contain the machine learning algorithms. In order to install AID, users' system must satisfy the following requirements:

* Operation Systems: Linux (generic) or macOS. We recommend to use Linux as the base system. For Windows, the users are suggested to use Windows Subsystems for Linux (aka WSL).
* Docker: The system must have installed docker on the system. For instructions, please take a look at [Get Docker](https://docs.docker.com/get-docker/).
  
Then users can install the pre-built AID binary by running the following command:

```
sudo curl https://releases.autoai.org/aid/install.sh | sudo bash -s -- edge
```

Once installed, users can start the web dashboard by running the following command:

```
aid up
```
