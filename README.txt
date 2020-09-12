Google Cloud Fundamentals: Getting Started with App Engine
##Google Cloud Fundamentals: Getting Started with App Engine

#Objectives

1.Initialize App Engine.
  
2.Preview an App Engine application running locally in Cloud Shell.

3.Deploy an App Engine application, so that others can reach it.

4.Disable an App Engine application, when you no longer want it to be visible.

#STEPS

1.Initialize App Engine.
    .Initialize your App Engine app with your project and choose its region:
        gcloud app create --project=$DEVSHELL_PROJECT_ID

    . select the region where you want your App Engine application located, or run this command:
        gcloud config set compute/zone us-central1-b
        
    .Clone the source code repository for a sample application in the hello_world directory:
          git clone https://github.com/GoogleCloudPlatform/python-docs-samples

    .Navigate to the source directory:
       cd python-docs-samples/appengine/standard_python3/hello_world

2.Preview an App Engine application running locally in Cloud Shell.

    .Execute the following command to download and update the packages list.
         sudo apt-get update

    .Set up a virtual environment in which you will run your application. Python virtual environments are used to isolate package installations from the system.
           sudo apt-get install virtualenv
             If prompted [Y/n], press Y and then Enter.
             
        .result:
             virtualenv -p python3 venv

    .Activate the virtual environment.
            source venv/bin/activate

    .Navigate to your project directory and install dependencies.
            pip install  -r requirements.txt

   .Run the application:
           python main.py

    .To access the Web preview icon, you may need to collapse the Navigation menu.
          click Web preview (Web Preview) > Preview on port 8080 to preview the application.

      .result:
           hello world!

3. Deploy an App Engine application, so that others can reach it.
    .Navigate to the source directory:
        cd ~/python-docs-samples/appengine/standard_python3/hello_world

    .Deploy your Hello World application.
         gcloud app deploy

    If prompted "Do you want to continue (Y/n)?", press Y and then Enter.
        This app deploy command uses the app.yaml file to identify project configuration.

    .Launch your browser to view the app at http://YOUR_PROJECT_ID.appspot.com
         gcloud app browse

    .Copy and paste the URL into a new browser window.
        .Result:
             hello world!

4.Disable an App Engine application, when you no longer want it to be visible.
        .In the Cloud Console, 
             App Engine > Settings > Disable application.

        . Enter the App ID and click DISABLE.
            refresh the browser window you used to view to the application site, you'll get a 404 error.
