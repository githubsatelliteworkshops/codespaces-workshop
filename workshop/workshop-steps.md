## Basic Codespace creation
1. Fork this repository into your user account (using Fork option on top right of the screen). This repository will get forked as <username>/codespaces-workshop.
This repository contains a sample REST API implemented via dotnet core

2. Then click on the Code drop down, you will see the option "Open with codespaces"<br>
![Open With Codespaces](./images/opencodespace.png)<br>It will take few minutes to create a workspace.

3. You will see a VS-Code editor with your project.<br>You now have a working dev environment in the browser to start development 🎉

1. Open the terminal from the editor's bottom pane
2. Execute ```dotnet run --project src/weatherforecast.api```
3. Your dotnet REST service should now be running
![terminal](./images/runproject.png)

4. Now click on the ```http://localhost:5000``` link in the terminal output and see the magic of port forwarding, allowing you to access your codespace dev box.
<br>However, you should be seeing nothing in the page as we don't have any index page yet. Just append the URL with the ```/weatherforecast```

5. You would see the REST API output in the browser

**Making Code change and debug**

**Create branch and raise pull request**

**Merge the changes**

## Customizing codespaces using devcontainer.json

#### Using custom devcontainer.json
GitHub Documentation [Link](https://docs.github.com/en/github/developing-online-with-codespaces/configuring-codespaces-for-your-project#creating-a-custom-codespace-configuration)

#### Using prebuilt configurations
GitHub Documentation [Link](https://docs.github.com/en/github/developing-online-with-codespaces/configuring-codespaces-for-your-project#using-a-pre-built-container-configuration)

**Option1** 

- Go [here](https://github.com/microsoft/vscode-dev-containers)
- Download the repository
- Copy the folder from ```<repo>/containers/dotnet-mssql/.devcontainer``` to your project root folder
- Open command palette in the browser (right click or cmd/ctrl+SHIFT+P)
- Run the command ```Codespaces: ReBuild Container```
  <br>This step will rebuild the codespace according to our specification in the devcontainer.json
- Now check the VS Code extensions, you should have SQL Server extension with the connection and an empty database ```ApplicationDB```

**Option2**
(**Recommonded**) : You can add the devcontainer configuration using a VSCode command
- Open command pallette 
- Run the Command ``` Codespaces: Add Development Container Configuration Files ```
- Type in the ```MS SQL``` in the search box
- Click on ```Show All Definition```
- Select C# & MS SQL and you are done !
- You will see bunch of files created in your repo root under ```.devcontainer``` folder


To read more details on available dev container [here](https://code.visualstudio.com/docs/remote/create-dev-container)

**Personalizing for your account**
- Codespaces uses your ```dotfiles``` repository on GitHub to personalize every new codespace that you create
  More details [here](https://docs.github.com/en/github/developing-online-with-codespaces/personalizing-codespaces-for-your-account)

- VSCode Settings Sync. Read more [here](https://code.visualstudio.com/docs/editor/settings-sync) for enabling the settings sync.

**Security**
GitHub Documentation for codespaces [security](https://docs.github.com/en/github/developing-online-with-codespaces/managing-access-and-security-for-codespaces)

**Secrets**
GitHub documentation for managing [encrypted secrets for codespaces](https://docs.github.com/en/github/developing-online-with-codespaces/managing-encrypted-secrets-for-codespaces)

All our codespaces secrets will be loaded as the Environment variables in the codespace environment.
