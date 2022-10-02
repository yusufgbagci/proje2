# Udacity Project 2

## Project Plan

Quarterly plan: <a href="https://docs.google.com/spreadsheets/d/1RamKHGMi_xrJnVlogC0iIhGUnDuygZJPrGm8gGxJI4Y/edit#gid=2120097640/" target="_blank">Quartelyplan</a> 


Weekly project plan: <a href="https://docs.google.com/spreadsheets/d/1RamKHGMi_xrJnVlogC0iIhGUnDuygZJPrGm8gGxJI4Y/edit#gid=1348135932/" target="_blank">weeklyplan</a> 


## Trello
Project workspace on Trello: <a href="https://trello.com/invite/b/i1jzP7lV/c72afa8d002a985b49e5d9bf83ef292e/mlops/" target="_blank">trelloplan</a> 


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



## Project Clone into Azure Cloud Shell

![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/ss1.jpg?raw=true)

This image is proof of connection between Azure Cloud Shell and Github.


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

### Verifying Remote Tests pass 

![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/ss4.jpg?raw=true)


## Continuous Delivery on Azure

This step involve setting up Azure Pipelines to deploy the Flask starter code to Azure App Services.

Firstly, in Azure bash must python app run;

```sh
python app.py
```
And then, Make prediction file can run;


```sh
./make_prediction.sh
```
![Source Code - Cloud](https://github.com/yusufgbagci/proje2/blob/main/ss6.jpg?raw=true)


### Also last step of project deploying Azure piplines showed in this video;


<a href="https://youtu.be/uZpi8ToOBbk" target="_blank">youtubelink</a> 

