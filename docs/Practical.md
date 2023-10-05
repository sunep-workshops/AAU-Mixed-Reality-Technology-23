# Practicalities
When working with both kinect and projection mappings, there are quite a few practical issues that you need to consider in your process.

## Projection mapping

### lighting
When you work with projections in general, you need to be aware of the lighting, lighting that is not your projection reduce your contrast in your image. Likewise if you project on surfaces that are less than ideal, you need to adress that.
- Control the lighting
    - Blind the windows
    - Turn off lights that are not needed
    - get the brightest projectors you can get your hands on
    - stack multiple projectors (advanced)

### Choosing a projector
When working with projection mapping it is important to choose the right projector for what you want to project onto. here are some considerations.

- Positioning -  you need to both cover all of what you are projecting onto as well as not have too bag of an image, thus wasting both light and resolution.
- Thow ratio - you want the longest throw ratio you can fit and get you hands on. short throw projectors have become increasingly popular everywhere, but for mapping, they are not very good as the angle onto the surface gets very narrow towards the edge of the image, just try to move a short throw prohjector slightly and see how the corners as well as image distortion get quite extreme.
    - Longest throw that can cover the projected object.
    - no short thow projectors!
- Resolution - if people are to see the image up close, you need all the resolution you can get, UHD is better than FullHD that is better than 720p. get as many pixels as you can get you hands on and that you computer can run at decent frame rates.

#### Calculate the image size from the throw ratio
The formula is simply

$$ Throw Ratio = \dfrac{Throw Distance}{Image Width} $$

Which can give you the following:

$$ Image Width = \dfrac{Throw Distance}{Throw Ratio} $$

$$ Throw Distance = Image Width \times Throw Ratio$$

When you calculate the position of the projector, you will base the calculations on the relevant dimension, meaning if you have a tall object, you use the height in combination with the image ratio to get the image width. You then use that info to calculate the distance you need to place the projectior at.

If you are lazy, you can use one of the many online projector calculators. most of the manufacturers have calculators that know their projectors. I recommend the one from projector central as they have models from across all brands:
- [Projector Central](https://www.projectorcentral.com/projection-calculator-pro.cfm)

- Lens Shift - You shouldn't need to account for lens shift (How high the image is shifted, relative to the projector position) when using either madmapper or badmapper.

### Madmapper
If you for some reason don't want to use Badmapper and instead want to use madmapper, you need to get the image from vvvv to madmapper. Two situations, madmapper on the same machine and madmapper on a separate machine. for this you have two options, that can also be used to send textures between instances of gamma and badmapper:

- Spout - Spout is included in Stride, the 3D engine, check out the help patch for sending and receiving textures via spout.
- [NDI](https://www.nuget.org/packages/VL.IO.NDI) - NDI send and receive textures over the network. it is surprisingly good and stable if you have a network without too much other traffic. it also work with audio.
    - `nuget install vl.io.ndi -pre`

Note that you will be sending flat textures and do to some degree loose the ability to adress a three dimensional object.

## Depth Cameras
At ArT we have access to kinect 360 and kinect one (Kinect 1 and kinect 2)
A depth camera is such a tool that seems to just work when you are testing but depending on how you plan to use it, might fail once there are many people in front of it.
Kinect 1 can track 2 skeletons, Kinect 2 can track 6.

I have worked with both and find working with skeletons tricky and only successfull if you can control the number of people in front of it. I will now any day prefer kinect 2 over kinect 1, as the sensors are much more robust in regards to lighting.

### Kinect One aka kinect 2
This is the one I am using in class, it is surprisingly robust when it comes to other lightsources. I have used it in direct sunlight and it worked great.
Multiple Kinect 2 can co-exist in the same space. Only one can track skeletons if they are connected to the same computer, You can however get the images from the various sensors from all of them.


### Kinect 360 or kinect 1
This is the OG kinect that started the whole thing. It is VERY sensitive to infraread light sources as it works by emitting a pattern of infraread dots. Multiple kinect 1 are tricky, it is possible with some tweaks like having a little motor shaking the kinect slightly.
It works horribly in daylight, if at all.

#### Specs
The most important spec is the field of view (FOV) of the different sensors. [This page](https://smeenk.com/kinect-field-of-view-comparison/) by [Roland Smeek](https://smeenk.com/) goes through the spcecs of both kinects. He even made [this handy tool](https://www.smeenk.com/webgl/kinectfovexplorer.html) to visualize FOV of the two versions.

### Other Depth Cameras

#### Azure Kinect
I have no experience with these sensors and we don't have any at hand. So here I pretend they don't exist.
If you get your hands on one, you will need these two packages:
- https://www.nuget.org/packages/VL.Devices.AzureKinect
- https://www.nuget.org/packages/VL.Devices.AzureKinect.Body

#### Intel Realsense
These exist somewhere at AAU but are not available for us this semester. Talk to Thomas about it if you are curious about them.
Like with the Azure version, I have no experience with these and will also pretend they don't exist. If you get one, you need this package
- https://www.nuget.org/packages/VL.Devices.RealSense

#### there are more
Microsoft and Intel are not the only ones that have made depth cameras. You can see which cameras that have a VL- nuget in the graybook
- https://thegraybook.vvvv.org/reference/libraries/depthcameras.html

