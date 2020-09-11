# LAB: Google Cloud Fundamentals: Getting Started with App Engine

## Objectives

In this lab, you learn how to perform the following tasks:

    - Initialize App Engine.

    - Preview an App Engine application running locally in Cloud Shell.

    - Deploy an App Engine application, so that others can reach it.

    - Disable an App Engine application, when you no longer want it to be visible.

## Steps:

- Open the Cloud Shell (gcloud command line) and list the active account name with this command:

        gcloud auth list

    The result should look similar to this

    ```
    Credentialed accounts:
     - google1623327_student@qwiklabs.net
    ```

    - List the project ID with this command:

        gcloud config list project

    The result should look similar to this

    ```
    [core]
    project = qwiklabs-gcp-44776a13dea667a6
    ```

1. Initialize App Engine


    - Initialize your App Engine app with your project and choose its region:

        gcloud app create --project=$DEVSHELL_PROJECT_ID

    - Clone the source code repository for a sample application in the hello_world directory:

        git clone https://github.com/GoogleCloudPlatform/python-docs-samples

    - Navigate to the source directory:

        cd python-docs-samples/appengine/standard_python3/hello_world


2. Run Hello World application locally


    - Execute the following command to download and update the packages list.

        sudo apt-get update

    - Set up a virtual environment in which you will run your application.

        sudo apt-get install virtualenv -y

3. Use python virtual environments as they are used to isolate package installations from the system.

        virtualenv -p python3 venv

    - Activate the virtual environment.

        source venv/bin/activate

    - Navigate to your project directory and install dependencies.

        pip install  -r requirements.txt

    - Run the application:

        python main.py

    - Test application locally using curl:

        curl http://127.0.0.1:8080


3. Deploy and run Hello World on App Engine


    To deploy your application to the App Engine Standard environment:

    - Navigate to the source directory:
    
        cd ~/python-docs-samples/appengine/standard_python3/hello_world

    - Deploy Hello World application

        gcloud app deploy -y

    - Launch your browser to view the app

        gcloud app browse

    - Copy and paste the URL into a new browser window.


