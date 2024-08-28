# Communication between ROV and Waterlinked

With both devices connected to the same computer, a network bridge needs to be created to allow the Waterlinked to communicate position data to the ROV.

This is easiest to setup on windows and can be accomplished by going to
Control Panel -> Network and Internet -> Network and Sharing Center -> Change adapter settings.
Then, select both the ethernet adapter used to connect to the waterlinked and the ethernet adapter used to connect to the ROV, and right click and in the context menu select "Bridge Connections". To assign the correct IP address to the newly created bridge, right click on it and select properties. Then, double click on Internet Protocol Version 4, and enter a static IP address of "192.168.2.1" and use the default subnet mask of "255.255.255.0" For more information and images see https://waterlinked.github.io/underwater-gps/integration/bluerov-integration-u1/

# IP Addresses

Laptop: 192.168.2.1
BlueROV: 192.168.2.2
Waterlinked: 192.168.2.94

The BlueROV and Waterlinked host web interfaces for further configuration and software updates.

# Getting the ROV internet at FAU

BlueOS doesn't currently support directly connecting to wifis that require a username or a sign-on page

- Enable network sharing from wifi to bridge
- ~~Go to blueOS webui~~
- ~~Get a terminal outside of docker~~
- ~~add laptop as gateway with "sudo route add -net 0.0.0.0 gw 192.168.2.1 netmask 0.0.0.0 dev eth0"~~
- ~~Doesnt seem to give the actual blueos container internet?~~
- I manually set the gateway in /etc/dhcpcd.conf

# Updating BlueROV without the ROV having internet

If the ROV doesn't have internet, Use the following steps, otherwise just use the BlueOS UI.

Download latest build of the master branch from https://github.com/bluerobotics/BlueOS/actions/workflows/test-and-deploy.yml
Or a stable release from https://github.com/bluerobotics/BlueOS/releases/

Make sure to download armv7 version
If you downloaded a zip file, extract the tar file it should contain

# SSH into BlueROV

ip: 192.168.2.2
username: pi
password: raspberry

# Working testing protocol

- Setup ROV
  - TODO
- Make sure all component's webuis are accessible from laptop
- Verify that the ROV is running the latest version of blueos
- TODO
 