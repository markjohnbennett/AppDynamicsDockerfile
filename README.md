# AppDynamicsDockerfile
Testing App Dynamics with Dockerfile

This is a generic project that I added the dockerFile just to see if I could get files off of the appsDynamic image

To run this:


C:\Users\mbennett1\Source\AppDynamicsDockerfile\TestAppDynamics>docker build -t myimage -f ./TestAppDynamics/Dockerfile .

That builds the image.

Now, start the image, and go into to bash mode to see what was copied.

C:\Users\mbennett1\Source\AppDynamicsDockerfile\TestAppDynamics>docker run -d -it myimage:latest
28dfe7ac82153dd5239887bc38b73e3d6dc77ab097a3bf6803c59fb9ed717a28

C:\Users\mbennett1\Source\AppDynamicsDockerfile\TestAppDynamics>docker ps
CONTAINER ID   IMAGE            COMMAND                  CREATED          STATUS          PORTS             NAMES
28dfe7ac8215   myimage:latest   "dotnet TestAppDynam…"   33 seconds ago   Up 27 seconds   80/tcp, 443/tcp   nostalgic_turing

Run a command in a running container

C:\Users\mbennett1\Source\AppDynamicsDockerfile\TestAppDynamics>docker exec -it 28dfe7ac8215 bash
root@28dfe7ac8215:/app# pwd
/app
root@28dfe7ac8215:/app# cd ..
root@28dfe7ac8215:/# dir
app  bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@28dfe7ac8215:/# cd opt
root@28dfe7ac8215:/opt# dir
appdynamics
root@28dfe7ac8215:/opt# cd appdynamics
root@28dfe7ac8215:/opt/appdynamics# dir
AppDynamics.Agent.OtelSDK.dll  AppDynamics.Agent.netstandard.dll  libappdprofiler.so  libappdprofiler_glibc.so  libappdprofiler_musl.so
root@28dfe7ac8215:/opt/appdynamics#
