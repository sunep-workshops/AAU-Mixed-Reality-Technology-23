# AAU-Mixed-Reality-Technologies-23

Before we meet on September 29, make sure each group have at least on windows 10/11 PC with the following installed (The kinect nodes will not work with earlier versions of windows):

- vvvv Gamma, latest stable version
    - https://visualprogramming.net/#Download
- Once vvvv is installed, install the Kinect 360 nuget
    - click the Quad menu in the top right corner and select >Manage Nugets>Commandline.
![Alt text](/img/NuGet-CMD.png)
the following CMD promt, you type the following: "nuget install vl.devices.kinect"
![Alt text](/img/CMD-kinect.png)
![Alt text](/img/CMD-Kinect-result.png)
- While you have the CMD prompt open, you should also install BadMapper and the addons - Lots of useful bits and peices
    - nuget install vl.badmapper -pre
    - nuget install vl.addons
- Now install the kinect SDK from microsoft https://www.microsoft.com/en-us/download/details.aspx?id=40278 and reboot your computer

You should now be able to use the Kinect in vvvv gamma.

## Finding help

When you first start vvvv, it looks something like this:
![Alt text](/img/GammaStart.png)
To the right you have the help browser.
![Alt text](/img/LearnTab.png)
If you click the Learn tab, you can search in everything that is installed and have a help patch. eg. Kinect.
![Alt text](/img/LearnKinect.png)
I will recommend that you look around and see what is possible, there is a lot of good inspiration to be found.

## Community
- The fastest way to get help if you are stuck is to post on the chat: https://app.element.io/#/room/#vvvv:matrix.org
- In the chat, you will often be asked to create a forum post with a deeper explanation https://discourse.vvvv.org/

## Notes on Computer specs.
Even though vvvv can run on modest hardware, a slow system will severely impact how much is possible with. a more recent system with a discrete GPU is highly recommended and needed for complex graphics at acceptable framerates.
og GPU's I will recommend 10th generation nvidia GPU or newer, GTX 1050 or better.
I am not too familiar with the AMD GPUss but similar GPUs from AMD should work just fine.

If your machine has a discrete GPU, it is probably fine 

### Assign vvvv to the discrete GPU
To  make sure that you are actually using the discrete GPU, in settings you go to System>Display>Graphics and select vvvv and choos high performance.

### Mac
Again, same story about discrete GPUs
- x86 - Bootcamp your mac and install windows - parallels might work, but can be a nightmare.
- M1 - Good luck, there are rumors that someone has gotten vvvv gamma to work, but the one time I have tried to get it to work, I couldn't get it to work, I didn't spend too much time on it. If you try this route, you will need to have vvvv gamma up and running on it, including all nugets before the 29th. there will be no time for troubleshooting after that.