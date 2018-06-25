# Poseidon Dev Host
## Installation
In order to start developing Poseidon Applications, you should get **poseidon-dev-host**. You can install from NPM globally:
```powershell
npm install @kognifai/poseidon-dev-host@latest -g
```

## Hosting
After you've globally installed  **poseidon-dev-host** you can start it with the following command:
```powershell
poseidon-dev-host
```
The console shows a message that it is now listening on http://localhost:8080. Opening the browser on this URL currently does not load anything as you need to get the Poseidon applications. Stop the dev-host now and proceed with the next step.

# Installing applications
Start by creating an empty directory in your local work directory:
```powershell
mkdir C:\kognifai\applications
cd C:\kognifai\applications
```
You can use NPM to install the applications:
```powershell
npm install @kognifai/poseidon-home@latest
npm install @kognifai/poseidon-user-profile@latest
npm install @kognifai/poseidon-user-administration@latest
npm install @kognifai/poseidon-test-pages@latest
```
You can now tell **poseidon-dev-host** to load and host these applications:
(Remember stop the **poseidon-dev-host** if it is currently running. You can do that by pressing Ctrl+C in the console)
```powershell
poseidon-dev-host --applications "C:\kognifai\applications"
```
The ```--applications``` parameter specifies the directory in which **poseidon-dev-host** will look for applications (including subfolder **/node_modules\@kognifai**). An application is considered a directory which contains content files (html pages, scripts, styles, assets, etc) together with application manifest file (**app.manifest.json**).
When the command is executed, the host should output a message listing all the applications' manifests it found, similar to:
```
Hosting applications from C:\kognifai\applications
Loading application manifests
	Home
	Test Pages
	User Administration
	User Profile
```
Open a browser at http://localhost:8080 in order to see the Poseidon platform. The host comes with a developer friendly security solution. Type in any username and password to log in. Then the platform is loaded, note the left hand side navigation menu with applications:

![image.png](.attachments/image-43ec7967-c093-468b-a63e-e64075349bdc.png)

# Creating a new Poseidon Application
## Installing Yeoman
If you have not yet installed Yeoman, you can do so by executing this command:
```powershell
npm install -g yo
```

## Installing the Yeoman generator
You can install the **kognifai-poseidon** Yeoman generator from NPM:
```powershell
npm install -g @kognifai/generator-poseidon@latest
```

## Using the generator
You should use the generator in the kognifai applications folder:
```powershell
cd C:\kognifai\applications
yo @kognifai/poseidon:application
```
Follow the instructions of the generator to fill in the required information. The name of the new app will be the same as the name of the folder (e.g. my-first-app). After the generator completes, you will have a working simple application. Start it:
```powershell
cd C:\kognifai\applications\my-first-app
npm start
```
Restart **poseidon-dev-host** and reload the platform in your browser. You should be able to see and open the newly created application from the navigation menu.
- You can use VS Code (or your favorite IDE/code editor) to edit the source code:
```powershell
code .
```
Any code changes you make on application pages, scripts and styles will be automatically reflected in the browser (live reload).
- You can use NPM scripts to start, build, lint, test:
```powershell
npm start
npm run build
npm run lint
npm run test
```

# Next Steps
To use the framework service see the respective wiki pages describing them and use the test pages application for reference.