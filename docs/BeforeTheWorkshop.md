# AAU-Mixed-Reality-Technologies-23


## Do Before September 29

### Insrtall vvvv Gamma and extra packages

Before we meet on September 29, make sure each group have at least on windows 10/11 PC with the following installed (The kinect nodes will not work with earlier versions of windows):

- Download and install vvvv Gamma, latest stable version (currently 5.2)
    - https://visualprogramming.net/#Download
- Once vvvv is installed, install kinect2, BadMapper and the addon pack
    - click the Quad menu in the top right corner and select >Manage Nugets>Commandline.
    ![Alt text](/img/NuGet-CMD.png)
    - in the command promt, type:
        - nuget install vl.devices.kinect2
        - nuget install vl.badmapper -pre
        - nuget install vl.addons

it will look something like this:
![bla bla](/img/NugetKinect2.png)
And then
![bla bla](/img/NugetKinect2Result.png)

- Now install the kinect SDK from microsoft https://www.microsoft.com/en-us/download/details.aspx?id=44559 and reboot your computer

You should now be able to use the Kinect in vvvv gamma.

To make sure that it is working, connect a Kinect2 (kinect one) device and then run the "Visualize the depth pointcloud" help patch, that you find by searching for kinect in the help browser.
![Alt text](/img/KinectPointcloud.png)

Similarly, you can check that badmapper is correctly installed by starting the help patch "Using Interactive BadMapper"
![Alt text](/img/Badmapper.png)

The addons adds amazing texture effects, so you can check out one of those, eg. the ASCII effect.
![Alt text](/img/Ascii.png)

## Notes on Computer specs.
Even though vvvv can run on modest hardware, a slow system will severely impact how much is possible with. a more recent system with a discrete GPU is highly recommended and needed for complex graphics at acceptable framerates.
og GPU's I will recommend 10th generation nvidia GPU or newer, GTX 1050 or better.
I am not too familiar with the AMD GPUss but similar GPUs from AMD should work just fine.

If your machine has a discrete GPU, it is probably fine 

### Assign vvvv to the discrete GPU
To  make sure that you are actually using the discrete GPU, in settings you go to System>Display>Graphics and select vvvv and choose high performance.

### Mac
Again, same story about discrete GPUs
- x86 - Bootcamp your mac and install windows - parallels might work, but can be a nightmare.
- M1 - Good luck, there are rumors that someone has gotten vvvv gamma to work, but the one time I have tried to get it to work, I couldn't get it to work, I didn't spend too much time on it. If you try this route, you will need to have vvvv gamma up and running on it, including all nugets before the 29th. there will be no time for troubleshooting after that.

Asking about experiences with M1/M2 macs and Gamma would be an excelent test of the forum, asking for any experiences on that matter.