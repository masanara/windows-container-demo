FROM microsoft/iis
SHELL ["powershell", "-command"]
EXPOSE 80

# Install ASP
RUN Install-WindowsFeature Web-ASP;

# Clean out default site
RUN powershell -NoProfile -Command Remove-Item -Recurse C:\inetpub\wwwroot\*

WORKDIR /inetpub/wwwroot
#Copy the app artifact in (assumes you are in the publish folder when building docker image)
COPY wwwroot/* ./
