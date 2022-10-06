# Udacity Project 2

## Project Plan

Quarterly plan: <a href="https://docs.google.com/spreadsheets/d/1RamKHGMi_xrJnVlogC0iIhGUnDuygZJPrGm8gGxJI4Y/edit#gid=2120097640/" target="_blank">Quartelyplan</a> 


Weekly project plan: <a href="https://docs.google.com/spreadsheets/d/1RamKHGMi_xrJnVlogC0iIhGUnDuygZJPrGm8gGxJI4Y/edit#gid=1348135932/" target="_blank">weeklyplan</a> 


## Trello
Project workspace on Trello: <a href="https://trello.com/invite/b/i1jzP7lV/c72afa8d002a985b49e5d9bf83ef292e/mlops/" target="_blank">trelloplan</a> 




## Project Clone into Azure Cloud Shell


![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/github_intg.jpg?raw=true)


```sh
git clone git@github.com:yusufgbagci/proje2.git

cd proje2

python3 -m venv ~/.myrepo
source ~/.myrepo/bin/activate
```





![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/ss1.jpg?raw=true)
This image is proof of connection between Azure Cloud Shell and Github




## Overview of the project

You can find Makefile, tests, and application scaffolding to test code locally in the Azure Cloud Shell.

![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/azure-cloud-shell.png?raw=true)


-In this step files:
- A Makefile
- A Requirements.txt
- A script file
- A test file
- A hello.py file
- A test_hello.py file

### Testing the test_python and Makefile

![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/ss2.jpg?raw=true)


![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/ss3.jpg?raw=true)





##  CI: Configure GitHub Actions

Configure GitHub Actions is project on change events in GitHub.

- yml code:
```sh
name: Python application test with Github Actions

on: [push]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Python 3.5
      uses: actions/setup-python@v1
      with:
        python-version: 3.5
    - name: Install dependencies
      run: |
        make install
    - name: Lint with pylint
      run: |
        make lint
    - name: Test with pytest
      run: |
        make test
```

![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/CI1.jpg?raw=true)

When commited the python.yaml file, the build automation will be build automatically.


![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/CI2.jpg?raw=true)

Updating the in the file make_predict_azure_app.sh


Before creating the Azure pipeline, it is necessary to run the stages locally as desired. For this reason, python app.py file is run by entering the same Azure account from two different pages at the same time.


Firstly, in Azure bash must python app run;

```sh
python app.py
```
![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/CI3.jpg?raw=true)


```sh
./make_prediction.sh
```
![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/ss6.jpg?raw=true)



### Verifying Remote Tests pass 

![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/ss4.jpg?raw=true)







## Continuous Delivery on Azure
This step involve setting up Azure Pipelines to deploy the Flask starter code to Azure App Services.

As a final step, we will run the website that we run locally in the cloud environment using Azure DEVOPS pipline. The benefit of this is that when a change is made to the main file automatically, you will not need to redo the whole change.


![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/pip1.jpg?raw=true)


Linked Github repo for this
Azure connection made with Appservice service
Created a new pipline

![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/pip2.jpg?raw=true)

It will now trigger CI on github actions for each commit and Azure pipeline will CI and deliver the update to webapp service (CD) via Azure Pipeline success


![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/pip3.jpg?raw=true)
### Also last step of project deploying Azure piplines showed in this video;


<a href="https://youtu.be/uZpi8ToOBbk" target="_blank">youtubelink</a> 

