# DevContainer

{% hint style="success" %}
To make the **Docker, Dev Containers** & **Remote- Development** on VS Code Works , You need to be sure that  the Extension Dev Containers is already Installed , otherwise it will not working even it let choose all needed parameters but in the end it will fail.
{% endhint %}

### Steps to create the VSCode DevContainer

1. Create the GitHub Repository.
2. Create the GitBook Document Namespace or collection and link it to GitHub Repository.
3. Clone the GitHub Repository on your `%USERPROFILE%\Desktop\PROJECTS` location.
4. open the newly created Project folder in Powershell.
5. Run the following command:

```powershell
# Create 4 new local folders 
mkdir script,src,log,app
# Add test file in each folder 
touch script\testscript.txt
touch src\tesrc.txt
touch log\testlog.txt
touch app\testapp.txt
# Note : Be sure of these files locations
```

6. Then Run **`Git`** Commands to push the changes to GitHub Repository (Refresh GitHub Repository to see the new changes):

```git
# check the Project location using pwd command
Git add .
Git commit -m " add 4 new folders with 4 test files"
Git push --force
```

7. use `Ctrl+Shift+P` to run the Creation of the DevContainer.

{% hint style="warning" %}
Try NOT to create a very complicated DevContainer, Start Simple.
{% endhint %}

8. When The Container is Created , add the following Lines to file `devcontainer.json`&#x20;

```json
// BF add: Add four project folders: logs,scripts,app and src 
	// let these folders be available also into the DevContainer
	"remoteUser": "vscode",
	"mounts": [
		"source=${localEnv:HOME}${localEnv:USERPROFILE/Desktop/PROJECTS/DevGisLAB/log},target=/home/vscode/dev/log,type=bind,consistency=cached",
		"source=${localEnv:HOME}${localEnv:USERPROFILE/Desktop/PROJECTS/DevGisLAB/script},target=/home/vscode/dev/script,type=bind,consistency=cached",
		"source=${localEnv:HOME}${localEnv:USERPROFILE/Desktop/PROJECTS/DevGisLAB/src},target=/home/vscode/dev/src,type=bind,consistency=cached",
		"source=${localEnv:HOME}${localEnv:USERPROFILE/Desktop/PROJECTS/DevGisLAB/app},target=/home/vscode/dev/app,type=bind,consistency=cached"
	]
```

9. Check the existence of the folders and the test files in the DevContainer , In case these files are not exists in the folders , try create new ones from within the DevContainer and check if they will be also created in the Project local folders or not?
10. After creating these files try to run the menu option of  **`Dev Containers: Rebuild Containers`**

{% hint style="danger" %}
Every time you got the Error , Try First to Edit the file devcontainer.json in Recovery mode  (Check for Spelling mistakes in the code), otherwise, Revert the changes from Git and Rebuild the Dev Container
{% endhint %}

<figure><img src="../../.gitbook/assets/18_devcontainers-rebuild-and-reopen-in-container.png" alt=""><figcaption></figcaption></figure>

11. After Editing the `devcontainer.json` file in recovery mode, rebuild the Dev Container using this command from the Command Palette: **`Dev Containers; Rebuild and reopen in Container`**

### In case the Error Percesisted

1. Restart Docker and VSCode: Try restarting both Docker and Visual Studio Code. This can help ensure a fresh start and clear any temporary issues.
2. Revert the changes: If the error persists, you can revert the changes to the previous mount location and see if the DevContainer works without any issues. This will help confirm if the changes to the mount location are causing the problem.
