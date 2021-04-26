# aws-lambda-layers
Repo of prepackaged .zip archives that contain Python libraries to be used with AWS Lambda.

## Available layers
* **praw-importer.zip** - Python Reddit API wrapper (https://praw.readthedocs.io/en/latest/)
* **requests-importer.zip** - requests http library (https://pypi.org/project/requests/)

## How to create layers
First make sure Python version is same as deployed in AWS Lambda instance. Install virtualenv if haven't already.
```
python3 -m pip install virtualenv
```
Create new directory, initialize virtual environment, and pip install required dependencies.
```
mkdir praw-importer
cd praw-importer
python3 -m virtualenv venv
source venv/bin/activate
pip3 install PACKAGE1 PACKAGE2
deactivate
```
Dependency files should now be availible in the following location.
```
cd venv/lib/{PYTHON_VERSION}/site-packages
```
Create `.zip` archive. Make sure the folder structure inside the zip file is as follows:
> python/lib/{PYTHON_VERSION}/site-packages/{LibrariesGoHere}