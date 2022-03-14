\pagebreak
# Specifications

## aid.toml

The ```aid.toml``` is the main entrance of a specific machine learning model. It has the following format:

``` toml
[package]
name="sentiment_prediction"
vendor="aidmodels"
tagline="Sentiment Analysis"
key=value // optional parameters

[[solvers]] 
name="sentimentSolver"
class="sentiment_prediction/solver/SentimentSolver"
```

The optional parameters includes:

```toml
gpu=true // indicate that a GPU is suggested.
```

Note: Currently, all the optional parameters are package-wise, i.e. users cannot set a specific parameter for certain solvers.

## pretrained.toml

The ```pretrained.toml``` indicates where to find and download the pre-trained weights and other assets. It has the following format:

```toml
[[models]]
name = "sentiment"
url = "https://github.com/.../v0.1/model.h5"

[[models]]
name = "some_file..."
url = "https://github.com/.../v0.1/somefile.h5"
```

AID will automatically fetch the pre-trained file and put them ```/pretrained``` folder under the project root.

Note: Though users can download files at initialization, just like [this repository](https://github.com/aidmodels/image_encoding), it is not suggested to do so as it will not allow AID to read the pre-trained weights for analysis and possibly conversion in the future. In the meanwhile, downloading at initialization requires downloading multiple times if users have re-created the container, which is less efficient and causes extra network traffic.
