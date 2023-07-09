# Git

Run the following Commands as soon as the Devcontainer is created

```git
git --version
git status
git commit -m " First commit from DevContainer"
# Pull the GitHub Repository of the Project inside DevContainer
git pull https://github.com/bahyway/DevAnacondaLAB.git
```

But then when You want to `Git Push` then the following <mark style="background-color:red;">**Error**</mark> will occur:

```git
vscode ➜ /workspaces/DevAnacondaLAB (main) $ git push
To https://github.com/bahyway/DevAnacondaLAB.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/bahyway/DevAnacondaLAB.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
vscode ➜ /workspaces/DevAnacondaLAB (main) $ 
```

### **NOTE**

Therefor , You need to know how to Develop the scripts ; within the Docker container or outside Docker Container but Inside the Project LAB which connected to GitHub Repository also, or you can connect both the Container and the Project to the same GitHub Repository (Check this solution).
