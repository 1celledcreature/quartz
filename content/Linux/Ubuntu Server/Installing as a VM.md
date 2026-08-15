When installing a Ubuntu sever, we first need an image. Head to https://ubuntu.com/download/server#architectures to download the .iso file.
Once we have the ISO file, we can import it into our virtualiser. I'm using UTM on mac.

Steps
- Click the + button at the top.
- Select 'emulate'
- Choose the ISO file downloaded.
- Follow the rest of instructions.

Next will be the installation:
When starting the VM, the following screen will appear
![[Pasted image 20241227144313.png]]

Use the first option

once selected, many commands will run for the preinstallation of the OS.
It may sit on this screen for some time but just leave it:
![[Pasted image 20241227144458.png]]

Choose the language once the screen pops up
On the next screen, choose the 'update to new installer' option if available
![[Pasted image 20241227144717.png]]

The original set up process may begin again.

Accept all the options unless you want to change any network settings.

Once it gets to the mirror test phase, you can hit 'done' once it gets to this point
![[Pasted image 20241227145206.png]]

Select storage configuration.

On the next screen, you want to change the settings so all the storage allocated to the VM is being used.
![[Pasted image 20241227145436.png]]
Navigate and select the highlighted option and change the amount to the max size
![[Pasted image 20241227145600.png]]
(In the above, i would change from 10 to 20)

There will then be a message stating the drive is about to be formatted. Hit ok.

Choose the login details and name of the server.

The next option is to install SSH. This will be used to remote onto the server so is advised to install.

You will then be presented with a bunch of server snaps. These help set the server up in a way that is best for the selected service's. These can also be installed at a later date.

The installation will then begin and can take some time to install.