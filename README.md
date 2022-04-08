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

## Setup/Test XQuartz and Docker Container UI Rendering.

This project involves running a UI *inside* a container and rendering it on the host OS. To do this we'll be:
- Installing XQuartz and instructing it to allow/accept network connections (Docker will connect using the local docker networking stack)
- Allowing/whitelisting connections to the X server from `127.0.0.1` (which is how Docker will connect)
- Running containers that connect to the X server to render their UIs.

### Installing/Testing
1. Install Xquartz via home brew (see below). Once Quartz is installed, you'll need to log out/in so that it can run. You should also have the `Allow connections from network clients` setting activated under `Preferences -> Security` to allow connections from Docker.
```
> brew install xquartz
```
2. Ensure that local network clients can connect to the X server by running:
```
> xhost + 127.0.0.1
```
3. Test the Xquartz/Docker setup by running a container which attempts to render a UI on the host OS from the docker container. We set the `DISPLAY` environment variable to `use the docker hostname for localhost (host.docker.internal) and send the UI to the zeroth (0) display.`
```
docker run -e DISPLAY=host.docker.internal:0 gns3/xeyes
```

### Running the Lab
1. Clone the repository
1. Open the repository root in VS Code
1. When prompted by VS Code, open in a remote container
1. After the container builds, VS Code may warn you there was an error installing the Uno extension. Accept the offer to "Install & Restart"
1. Run the following command at root: `cp ~/.Xauthority /workspaces/ffthh-uno-intro/`