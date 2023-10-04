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

If you are laze, you can use one of the many online projector calculators. most of the manufacturers have calculators that know their projectors. I reccomend the one from projector central as they have models from across all the brands:
- [Projector Central](https://www.projectorcentral.com/projection-calculator-pro.cfm)

- Lens Shift - You shouldn't need to account for lens shift (How high the image is shifted, relative to the projector position) when using either madmapper or badmapper.

### Madmapper
If you for some reason don't want to use Badmapper and instead want to use madmapper, you need to get the image from vvvv to madmapper. Two situations, madmapper on the same machine and madmapper on a separate machine. for this you have two options, that can also be used to send textures between instances of gamma and badmapper:

- Spout - Spout is included in Stride, the 3D engine, check out the help patch for sending and receiving textures via spout.
- [NDI](https://www.nuget.org/packages/VL.IO.NDI) - NDI send and receive textures over the network. it is surprisingly good and stable if you have a network without too much other traffic. it also work with audio.
    - `nuget install vl.io.ndi -pre`

Note that you will be sending flat textures and do to some degree loose the ability to adress a three dimensional object.

## Kinect
Kinect is such a tool that seems to just work when you are testing but depending on how you plan to use it, might fail once there are many people in front of it