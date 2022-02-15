# Introduction #

This project demonistrates visual studio code dev container concept.

# Notes #

1. You need to run this in Visual Studio Code.
2. Docker must be installed and running.
3. [Vs Code Remote Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) is needed.
4. Take a look at the file devcontainer.json file inside of .devcontainer folder. You should fine the following line of code.

```sh
dotnet dev-certs https --trust; dotnet dev-certs https -ep "$env:USERPROFILE/.aspnet/https/aspnetapp.pfx" -p "SecurePwdGoesHere"
```

5. You should run that command in a powershell. This will create a certificate in the folder which will look something like this in Windows
"C:\Users\Mewurk\.aspnet\https". Furthermore, this will also assign a password which is in this case 'SecurePwdGoesHere'.

6. Also in the same file, take a look for the following. Note the same password - 'SecurePwdGoesHere'

```js
	"remoteEnv": {
	    "ASPNETCORE_Kestrel__Certificates__Default__Password": "SecurePwdGoesHere",
	    "ASPNETCORE_Kestrel__Certificates__Default__Path": "/home/vscode/.aspnet/https/aspnetapp.pfx",
	},
```

# How to run #

1. From the command platte find Remote-Container: Reopen in container.
2. When this command executes Visual Studio Code will reopn in a different mode. It will connect to a Vs Code server inside of a container. 
3. Press F5.

# References # 
1. https://code.visualstudio.com/docs/remote/containers



