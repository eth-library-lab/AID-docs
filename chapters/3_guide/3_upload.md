## Propose New Models

### Prepare Necessary Files

*Step 1*: Download Project Template

First, users will need to run ```aid new``` command. AID will prompt users to input some information about the new model, as shown below:

![Command for Creating New Repository](./images/new_repo.png)

Note: AID will automatically create a new folder when download the template, so there is no need to create the folder beforehand.

*Step 2*: Modify the Solvers

After downloading the template, AID will generate a folder with the structure below:

![File Structure of a New Repository](./images/newrepo_structure.png)

where the folder ```ocr``` is the package name that users have specified in the previous step.

A sample solver is provided in ```ocr/solver.py```, with the content as shown below:

```python
from mlpm.solver import Solver
class SampleSolver(Solver):
    def __init__(self, toml_file=None):
        super().__init__(toml_file)
        # Do the initialisation here
        self.classifer = get_classifier()
        self.ready()
    def infer(self, data):
        # if users need to get file uploaded, get the path from input_file_path in data
        image = load_image(data['input_file_path'])
        result = self.classifier(image)
        return result # return a dict
```

users can now modify the constructor ```__init__``` function and the ```infer``` function as users wish. 

* The constructor is supposed to load the pre-trained models, and initialise all parameters that needs to be loaded.
* The ```infer``` function is supposed to read the input parameter ```data```, perform the inference process and return the results.

users can also change the name of the class, but make sure to update it in the ```aid.toml``` file.


*Step 3*: Checklist

After modifying everything, users can quickly check if the following requirements are met:

* The solver class in the ```aid.toml``` file should be readable by Python program, i.e. it should has the following format ```{packageName}/solver/{className}``` where ```packageName``` should be replaced by the package name that users have speicified before and ```{className}``` is the name of the class that users modified in step 2.

* If the pre-trained weights are needed, the weights should be uploaded somewhere accessible to users.
* All requirements should be noted in ```requirements.txt```.
* If additional software is needed, they should be noted in ```setup.sh```. In this file, users can write commands like ```apt-get install xxx``` to install additional dependencies that cannot be installed by ```pip```.
* Required request parameters and the meaning of output should be written in the ```README.md``` file.

### Build Models Locally

Once the model is prepared, users can start to build it locally in standalone mode. By doing so users can verify if the model will work properly in the Docker environment.

First, switch into the package folder, i.e., where the ```aid.toml``` is located. Then run ```aid build --path=./```. AID will automatically generate required docker files and build the project.

After the build is done, users can create the docker container by running ```docker create -p {host_port}:8080 {image_hash}```. Then users will see the hash to the created container in the terminal. users can use ```docker start {container_hash}``` to start the container and test it with the own input. users probably need some HTTP client, e.g., ```curl``` for testing.


### Upload to Model Hub

Once the model is ready locally, users then may need to upload it to the AID Model Hub. To do so, users need to first upload the model to GitHub, and then import the model to the AID Model Hub. Users will also need an account on the AID Model Hub.

The import process is as follows:

* First, the users need to sign in to their AID account on the AID Model Hub, and link it to their GitHub account. Once signed in, users can go to the ```Profile``` page on the AID Model Hub and find the models they want to sync.

![Find Models to Import](./images/import_1.png)

* Next, users simply click confirm, and the model will be imported. AID Model Hub will print the ```README.md``` file to double check if the model is exactly the one that the users want to import.

![Model Information](./images/import_2.png)

* Once confirmed, users can click the save button at the bottom of the page.