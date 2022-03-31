# ffthh-uno-intro
A repository for setting up and playing with uno for the first time

# Windows Setup
1. Clone the repository
1. Download and install VcXsrv from here: https://sourceforge.net/projects/vcxsrv/
1. Create a desktop shortcut to the VcXsrv.exe with the following target: "`{ path to your install }\vcxsrv.exe`" -multiwindow -clipboard -wgl -auth "`{ path to your cloned repository }\.Xauthority`" 
1. Open the repository root in VS Code
1. When prompted by VS Code, open in a remote container
1. After the container builds, VS Code may warn you there was an error installing the Uno extension. Accept the offer to "Install & Restart"
1. Run the following command at root: `cp ~/.Xauthority /workspaces/ffthh-uno-intro/`

# (Optional) Windows + Visual Studio Setup
1. Update Visual Studio with the following packages
    * Universal Windows Platform Development
    * Mobile development with .NET (Xamarin)
    * ASP.NET and web develeopment
    * Uno Platform Solution Templates (This is an extension)
1. Install .NET Core 5.0 SDK
1. Install the latest JDK (to build and run Android)


# MacOS Setup
1. Clone the repository
1. Download and install XQuartz from here: https://www.xquartz.org/
1. [Placeholder]
1. Open the repository root in VS Code
1. When prompted by VS Code, open in a remote container
1. After the container builds, VS Code may warn you there was an error installing the Uno extension. Accept the offer to "Install & Restart"
1. Run the following command at root: `cp ~/.Xauthority /workspaces/ffthh-uno-intro/`