

# 3D and Virtual Reality data visualisation for researchers

#### Activity Overview
There is growing interest in the use of virtual reality (VR) for research. The immersive spatial environment offered by VR offers new ways to gather and draw insights from research data. 
More broadly, 3D visualisation is useful for understanding complex data, and can be used to explore and share data visualisations on mobile devices and the web. 
This hands-on workshop will introduce participants to some of the equipment, software and processes involved in using 3D and VR to visualise research data. 
Participants will also be given the opportunity to use VR to interact with research data.

#### Target audience
Researchers with an interest in learning more about 3D and VR visualisation techniques, content is aimed at an introductory level - no programming experience required. 

#### Learning Outcomes
At the end of this workshop participant will be able to:
1. Identify how 3D visualisation and VR can potentially be used to draw insights from research data.
2. Recognise basic hardware and software requirements to visualise research data using 3D/VR.
3. Understand some 3D visualisation concepts and types of data that can be used to render 3D graphics and how these principles might be applied to their own research data.
4.  Gain hands-on experience using VR to interact with research data.

#### Prerequisites
 - Prior skills : none mandatory, familiarity with a programming language useful for more advanced content
 - Pre-reading : optional, see links section below
 - Equipment: VR equipment provided, bring own laptop so you can access materials during the workshop

## Useful Links
I am placing all the links we use throughout the workshop along with further reading and Monash resources here. (This is work in progress and will continue to be updated)

Etherpad:
 - Please visit this site and add your name to the list, we will use it for sharing notes or commentary during the workshop https://pad.carpentries.org/3dvis
 
Reading resources, optional:
 - https://medium.com/@KristianBouw/the-comprehensive-guide-to-getting-started-in-virtual-reality-c6a6419cf8cf
 - https://parameters.ssrc.org/2018/07/knowledge-in-3d-how-3d-data-visualization-is-reshaping-our-world/
 - https://serialmentor.com/dataviz/ "Fundamentals of Data Visualization" 

Monash:
 - https://www.monash.edu/researchinfrastructure/mivp
 - https://ialab.it.monash.edu/
 - https://sensilab.monash.edu/
 - https://www.monash.edu/data-fluency

Tools:
 - Python : Anaconda https://www.anaconda.com/distribution/ nteract : https://nteract.io/
 - Google Colab https://colab.research.google.com
 - Unity3D https://unity3d.com/
 - WebVR : https://webvr.info/ A-Frame https://aframe.io/
 - LavaVu : https://github.com/okaluza/lavavu
 - PreVis Prototype : https://mivp-dws1.erc.monash.edu:3000/
 
Visualisations:
 - 3D network : https://bl.ocks.org/vasturiano/972ca4f3e8e074dacf14d7071aad8ef9
 - Global wind https://earth.nullschool.net/
 - Anatomical : http://cave2.github.io/websurfer/?model=examples/quayle_kookaburra 
 - Updated Kookaburra surface model http://mivp.github.io/VizNotes/examples/kookaburra.html
 - PreVis Melbourne City point cloud https://mivp-dws1.erc.monash.edu:3000/pointviewer/?tag=335663
 - Inside the body VR demo https://thebodyvr.com/anatomy-viewer/
 - Demo notebooks on Google Colab https://drive.google.com/drive/folders/1V6cAZke7_wRLYlZbPkI9a5IB-mxe-GEy?usp=sharing
 - Laos Plain Of Jars http://mivp.github.io/VizNotes/examples/laos.html
 - Rabbit lung volume render http://mivp.github.io/VizNotes/examples/rabbit.html

Data sources used in examples:
 - Terrain (Aus) http://www.ga.gov.au/scientific-topics/national-location-information/digital-elevation-data http://elevation.fsdf.org.au/
 - SkyMap: https://opensky-network.org/
 - 3D Scanning : https://www.agisoft.com/ https://play.google.com/store/search?q=3d%20scanner 
 - Kookaburra model https://peerj.com/articles/355/#3Dvisualisation

## Intro:
### Definitions: Data Visualisation, 3D visualisation, Virtual Reality
 - Data visualisation is a broader topic with increasing relevance to all research, and ties in particularly with the increased application of data science and machine learning to research data.
 - 3D visualisation is a subset of data visualisation with a long history of use in science for visualising computational research data
 - Virtual reality technology is a new way of engaging with these kinds of visual datasets for both analysis of data and outreach and communication of research data results

### Big Data?
Just like in industry, research data is increasing rapidly in volume, velocity and variety. 
Many researchers now have "big data" problems. 
Visualisation is one aspect of data science that can help comprehend even very large data sets.
![visualisation as aprocess](https://mivp.github.io/VizNotes/images/process.svg)

### At Monash?
At the Monash Immersive Visualisation Platform (MIVP) https://www.monash.edu/researchinfrastructure/mivp we are more oriented to the 3D vis and scientific visualisation area, but constantly expanding our expertise.
We maintain a number of visualisation facilities, including VR (headset and the room-scale CAVE2).
We also provide services creating 3D visualisations for researchers, from helping to create tools to analyse data visually to generating compelling visualisations for outreach and publication.

![CAVE2 at MIVP](https://mivp.github.io/VizNotes/images/cave2build.jpg)

The Faculty of IT is also heavily involved in the visualisation and virtual reality spaces, in various fields including data science research and the Human-Computer Interaction, Immersive Analytics (https://ialab.it.monash.edu/) and SensiLab (https://sensilab.monash.edu/) research groups.
Mostly based at the Caulfield campus, they utilise VR equipment in research projects across IT and the Arts.

There are also many other independent VR projects at Monash that have engaged VR content creation studios or research software developer resources to build VR content for specific projects. Increasingly these involve the use of VR spaces as an environment for conducting research.

## Why 3D visualisation?
Mu Cephei IC 1396 Nebula *From hubble telescope*
![Mu Cephei](https://mivp.github.io/VizNotes/images/cephei_left.png)
*Emulated 3D animation: J-P Metsävainio*
![Mu Cephei 3D animated](https://mivp.github.io/VizNotes/images/cephei_right.gif)
3D vis, or scientific visualisation is a subset of Data Visualisation - the communication of data by visual means.
Right now we are interested in 3D Visualisation as this is a set of techniques that allows us to produce 3D renderings that can be used on both desktops, handhelds and virtual reality headsets.

 - Developed to represent 3D phenomena, eg: from instruments or simulations, with an emphasis on realistic rendering, perhaps with the addition of a time component (animation) (https://en.wikipedia.org/wiki/Scientific_visualization).  Think of recreating the experience of looking through a microscope, but for data generated by computers (simulations) or processed through computers (scanning techniques: instruments).
 - Data Visualisation methods and tools can also be applied (plots/graphs/relational maps etc).
 - We are still working with 2D images as the final output, all our displays are flat 2D planes:
 - 3D Vis requires translation to 2D Image from particular viewpoint from an infinite number of possible views and is impossible to encapsulate in a single image.

![3D Projection](https://mivp.github.io/VizNotes/images/perspective.png)
Using modern graphics processing hardware we can create an illusion of a 3D world or view to examine and analyse a model.
We have the video games industry to thank for the fast acceleration and widespread availability of these techniques which used to be only possible with extremely expensive specialist computing equipment.

These high end graphics processors are much more widespread than they used to be, but for visualising large data sets, especially in VR you will still need better graphics capability than is available on the average laptop or mobile device, ie: a high end graphics workstation.
However, high end graphics resources are now increasingly available on cloud platforms, such as AWS, NeCTAR and Google Colab (mostly due to demand from AI research).

*Two views of geological layers beneath the east coast of Australia*
![Australia East coast geology](https://mivp.github.io/VizNotes/images/eastcoast.png)![Australia East coast geology](https://mivp.github.io/VizNotes/images/eastcoast-sideview.png)

Research publications have been slow to adopt 3D visualisation, it does not work with traditional publication methods. There is increasing demand for interactive 3D in publication and it is changing, eg: this article from 2014 https://peerj.com/articles/355/#3Dvisualisation includes an interactive WebGL model viewer, while still including multiple views in the 2D figures
> NOTE: FigShare now supports 3D model data with an inline WebGL viewer

![Representing a 3D model in a 2D publication](https://dfzljdn9uc3pi.cloudfront.net/2014/355/1/fig-4-1x.jpg)
One way to classify visualisations is into "realistic" and "abstract" plots.
 - In 2D the most basic realistic plot is a photograph, but this also includes cartoon style drawings of real phenomena, eg: a map or a simplified line drawing highlighting some particular features. This attempts to convey data as if it was a scene one is looking at in the real world, but perhaps from an unusual viewpoint or with some data omitted or added. The map example distils real landscape features into a scaled down, top view version but is still representative of how the world looks from a birds eye view.
 - In 3D this type of plot attempts to construct a realistic 3D view and is the more common technique, with a clearer mapping between the artificial 3D world and a concept in the real world.
![enter image description here](https://camo.githubusercontent.com/efcd708e51234614fac1695b863327e78270cfa9/687474703a2f2f6f77656e2e6b616c757a612e69642e61752f536c696465732f323031372d30382d31352f636f6d62696e65642e706e67)
 - Abstract: graphs etc provide heavily stylised ways of representing data, by plotting on a set of axes or with links to relate data elements or groups to each other, these use familiar shapes and concepts to generate a mental model of the data without attempting to represent it in a visually realistic way. This is very heavily used in 2D, but you can still do this in 3D, the simplest example being a scatter plot on 3 axes - but 2D techniques such as this don't always translate well! You need to think differently in 3D.
 - Most of what people think of as data visualisation, including interactive 2D plots falls into this category.

![enter image description here](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0f/Oldfaithful3.png/320px-Oldfaithful3.png)![enter image description here](https://upload.wikimedia.org/wikipedia/commons/c/c4/Scatter_plot.jpg)

 - These two types of representation are often combined to good effect - for example, plotting cities as circles on a map (a realistic spatial visualisation) by representing the population with the size of the circle (abstract). Or using colour to represent other non-spatial information.

![enter image description here](https://upload.wikimedia.org/wikipedia/commons/thumb/e/eb/DChomicides.jpg/300px-DChomicides.jpg)
*Charles Minard's famous 1869 chart showing the number of men in Napoleon’s 1812 Russian campaign army, their movements, as well as the temperature they encountered on the return path*
![Minard Visualization](https://upload.wikimedia.org/wikipedia/commons/2/29/Minard.png)

In 3D, especially VR you usually want to create at least a baseline of a real world environment to plot your abstract data, such as a room or even just a ground plane, so people viewing can orient themselves, this helps avoid VR triggered motion sickness .
Techniques used in 2D do not always translate well to 3D however, and VR is a new paradigm, so think creatively about how you want to work with your data in VR, sticking to methods designed for output to 2D will be limiting.

### Reasons we might want to visualise in 3D?
Some good reasons you might want to use 3D visuals:
 - The data is inherently 3D (eg: 3D models, scans, geospatial data that includes the height axis)
 - The data is abstract and difficult to condense to 2D or comprehend with a 2D plot
 - The data can be mapped to an inherently 3D dataset, eg: can be plotted on a geospatial 3d dataset to map to locations
 - For fun / outreach / increased impact : humans find 3D visualisations more compelling than flat 2D images, but with that in mind...

![Australia East coast geology](https://mivp.github.io/VizNotes/images/eastcoast.png)
### When not to use 3D?
Excessive use of 3D just for the sake of it is generally not a good idea, for example, see this chapter in "Fundamentals of Data Visualization" [https://serialmentor.com/dataviz/no-3d.html](https://serialmentor.com/dataviz/no-3d.html) which points out that 3D extensions of traditional 2D plots are often very difficult to interpret correctly.
- If you can communicate your data clearly in a 2D plot
- If adding a 3rd dimension just provides too much visual information and complexity without adding anything

If your purpose is the accurate communication of data, such as in publication, these reasons for avoiding 3D are more important. If you are creating a visualisation for exploring research data or experimenting with simulated environments the benefits can outweigh these downsides significantly.

## Virtual Reality

### Why/when to use Virtual Reality in particular?
 - Where full immersion in data and 360 view is more useful than an overview
 - When interaction with visualised data/objects using VR controls would be more intuitive than point & click / keyboard / touchscreen
 - Where the extra level of immersion and realism helps create a more effective environment for research, eg: observing reactions of subjects to a simulation.

VR can be used to interrogate data spatially and find features using our inherent ability to explore 3D spaces using visual sensory information.
As an extension of 3D visualisation, it can further increase the impact and absorption of information into memory.  ("People recall information better through virtual reality" https://www.sciencedaily.com/releases/2018/06/180613162613.htm)
VR environments can also be used to research how people react to simulated environments or situations (see: Psychology Researchers at King's College https://www.kcl.ac.uk/ioppn/depts/psychology/research/researchgroupings/vrrg/projects-at-the-virtual-reality-research-group.aspx).

If you already have a 3D visualisation then getting it into VR is just the first step. Creating really compelling VR experiences requires more work than just getting your data up on the screens, though. Interaction with the data must be designed to work in the VR environment using VR specific controls.

### VR Equipment Overview

#### Types of VR hardware
 What makes one VR system different to another is typically:
  - How it displays graphics (does it turn a room into a virtual space, or simulate everything?)
 - How it tracks your movement (an important part of virtual reality is natural movement)
 - Where the graphics come from (does the device do the 3D heavy lifting, or does an external computer do that?)
 - How you interact with it (does it have tangible controllers, or do you use e.g. gaze control?)
 - If you need to wear any equipment (which can be the entire VR device!)
 ![CAVE2](https://mivp.github.io/VizNotes/images/cave2.png)
**Room scale**
 - Can be an entire dedicated facility, such as the CAVE2 (like we have at MIVP) and others
 - The huge size means that it can involve massive displays, projectors or large screens
 - Virtual experience comes naturally from being surrounded by large 3D graphics
 - Because it's in a fixed location (and it's large) it can be supported by very substantial computing power
 - Good for very detailed 3D data, and great for shared experience
 - Can move around a little bit without having any motion tracking, and it's still pretty convincing
 - However, very expensive ($ millions), very substantial investment of resources to build and operate, and writing software is specialised
![HTC Vive](https://mivp.github.io/VizNotes/images/vive.png)
**Head-mounted displays** (tethered, self-contained and wireless)
 - Portable devices that mimic large spaces by putting a small screen in front of your eyes
 - Needs to track your movement so that it feels like you're moving around in the virtual space, and track controllers so you can interact with the virtual space smoothly
 - Wearable nature is good and bad - comfort issues, lack of interactivity with other people
 - Detail is limited due to processing/3D rendering power, number of pixels on the screen, lenses
 - Some compromises for 3D quality:
        Tethered systems (Oculus Rift, HTC Vive) let a desktop computer or laptop do all the 3D graphics work - good for quality, but you're always on a leash
        High quality tracking feels very natural but requires external stations to be setup in the room
 - The newest systems (Oculus Go, HTC Quest, etc.) are self-contained, made up of essentially a mobile phone processor in a headset
        No cables, lightweight, but graphics quality is limited and the system depends on batteries (battery life, heat, etc.)
 - Wireless VR combines the two by streaming video from a desktop PC to a headset - supposedly good but expensive and requires a very powerful PC
 
**Mobile head-mounted displays**
 - Passive headsets that contain only VR optics (but no display or processor) can turn a mobile phone into a VR headset (Google Cardboard, countless no-name headsets you can buy just about anywhere)
 - Tracking is not great - movement can be uncomfortable, phone weight/size unpredictable
 - Some more sophisticated options exist (e.g. Gear VR, Google Daydream), but compatibility is limited to a small range of expensive phones
 
Atrificial Reality (AR) equipment is a whole other area which we'll leave for another time...

### Software: What tools can create a 3D visualisation from our data:

#### Methods requiring programming skills:

1) Use a visualisation library or tool that can create 3D plots or models - these usually create abstract plots of data or are tools designed for scientific visualisation work.
 - Libraries usually work within a given programming environment (Matlab, Python, R, Web)
   (Matplotlib, D3, Plotly, GGPlot, LavaVu)
- Currently many of these 3D plotting tools do not produce output for VR, they are for desktop or handheld device viewing only but this is changing.

2) Use a game development engine, Unity3D, UnrealEngine etc

#### Methods not requiring programming:

3) Use a desktop tool such as scientific visualisation or 3D modeling application
- These are usually desktop applications designed for visualisation provide an all-in-one environment (ParaView, VisIt, Drishti)
- 3D modeling applications such as Blender and Maya allow hand editing of 3D meshes
- Some of these desktop apps have built in VR support

4) Use our "Previs" web portal to upload a data set, and view it using our tools
 - Easiest way to get started, and this is what we'll demonstrate today in the workshop.
 - These tools are a work in progress but are intended to make it easy to access VR techniques by researchers, by supporting common types of data that can be visualised.

--------
### Software: What tools can turn a 3D visualisation into a VR experience:
- Moving forward more visualisation libraries like those mentioned above will support VR output directly which should make things easier. WebVR is helping with this, allowing WebGL visual output to be rendered to head mounted VR devices.

  - Desktop 2D displays have widely-accepted standard software applications that view or manipulate data, VR systems don't (yet?)
 - Usually needs some application-specific software that can read your data and display in 3D for the VR device
 - For a room-scale system, this can be something of a specialised field - outside of the scope of this workshop!
 - Recently, games engines have become a de facto standard way of making interactive VR software
        Unity3D and Unreal Engine are particularly popular and have extensive support for most mainstream HMDs, including mobile/self-contained devices
        Requires moderate programming skills but possibilities are endless and there are huge programmer communities for support
        However, getting large data sets into a game engine and still achieving game-like performance is a frequent challenge without a single one-size-fits-all solution
 - Web development standards and libraries are starting to include VR support; this has been a slow effort but things are improving
        Web developers with 3D graphics programming experience can use technologies such as WebVR to build VR apps into web browsers - open a page in a browser and a VR experience runs in your HMD!
        More accessible tools such as A-Frame open up VR development to web developers who aren't familiar with 3D libraries like OpenGL
 
#### MIVP Previs
 - As mentioned, MIVP's 'previs' service creates a simple workflow for getting static 2D and 3D data into a visualisation and from there into room-scale, desktop, Web and HMD viewers
We maintain viewing software for a number of platforms, and the service takes your data and lets the viewer software access it from the device of choice, or inside the CAVE2

## 3D input data for visualisation software:

### What data can we use and how do we visualise it?

### 3D / 360 video content

The easiest way to generate VR headset content is to film using a 360 camera, if you have access to one of these you can create realistic visualisations in 3D and VR of any real location.
Of course there is no interactive control of the path, it's a passive experience with some interaction giving control of the viewpoint direction only.

But, if we want to view data that can be interacted with in more dimensions, to walk through, for example - then we need to create a 3D visualisation first...

### How to render a 3D scene: Turning a dataset into a 3D object

The first step in visualising data in 3D is to translate it into a data type that can be easily rendered into a 3D scene.
Some data already matches nicely with one of these types, but other sources will need you to come up with a way to turn more abstract data into 3D spatial representations.

The three most widely used data types for this task are Points, Meshes and Volumes. Each have different properties and uses and techniques exist to translate data between these types. 

#### Point 
![Point cloud](https://mivp.github.io/VizNotes/images/points.png)
Fast and simple: the most basic kind of data to plot in 3D, requires an X,Y,Z coordinate, plus some rendering parameters (size/colour/shading etc) (which can be tied to further data values or represent real colours)
 - LiDAR / Photogrammetry : Quick recreation of a real world scene or object from photographic footage or laser scans (AgiSoft PhotoScan, Phone based 3D scanning)
 - Points as data points : points can be used to show elements of more abstract data types or even represent moving objects

#### Mesh
![Triangle Mesh](https://mivp.github.io/VizNotes/images/mesh.png)
The building block of most 3D graphics : used to create the illusion of objects by drawing the surface only (via a connected "Mesh" of triangles)
Used as the basis for drawing more complex objects, from simple shapes (sphere, cube, arrow) to detailed 3D models (people, terrain, anything that has a surface)
 - Created in 3D modelling applications (Blender, Maya)
 - Can be created from the real world via 3D scanning (to point cloud, then further processing to a mesh)
 - Can be extracted from Volume data (isosurface) or generated from a dense point cloud.

#### Volume
![Rabbit Lungs](https://mivp.github.io/VizNotes/images/lungs.jpg)
Think of stacks of 2D images : resulting in cubes of data points on a regular grid in 3D
 - Direct result of 3D image scans : microscopy, CT scans, MRI scans
 - 3D Simulations and numerical models
 - Can plot directly via Volume Rendering - slow but often very fine quality rendering or extract surface or point data for simpler plots (slices, isosurfaces)

#### Line
Not as frequently used, but another common primitive data type, useful for linking data objects, drawing map outlines, or tracing positions.

Other elements can be rendered, usually made up of these simple types : points, lines and/or triangle meshes.
These can all be combined to create more complex visualisations.

## Demonstrations (3D)
[Previs](https://mivp-dws1.erc.monash.edu:3000/)
PreVis - prototype is usable and open to public, but don't use with data you don't want others to have access to. New version coming this year with improved access control and visualisation tools.

[LavaVu](https://github.com/okaluza/lavavu)
- A pathway from python and IPython to 3D visualisation and VR, allows combining data into more complex visualisations - see example : IPython interactive 3D output via LavaVu running on Google Colab 

If you want to try running some 3D visualisation examples in IPython on Google Colab, I have shared a couple of example IPython Notebooks using publically available data sources.

Google Colab is an online interactive IPython notebook based environment intended for Machine Learning research that allow executing code on a remote machine hosted by google. These machines have high end graphics processors available so we can use them to do some 3D visualisation without having to install software on your own machine.

This is a bit of an experiment, so feel free to try it out while waiting to have a turn on the VR headsets but there may be technical issues as it hasn't been widely tested yet... basic steps are:

 - Sign in to google, eg: with your Monash account - you must be signed in to open the examples in Colab.
 - Open this link https://drive.google.com/drive/folders/1V6cAZke7_wRLYlZbPkI9a5IB-mxe-GEy
 - Choose one of the example notebooks, FlightPaths or SurfaceModels, double-click to open
 - Select "Open with Colaboratory" at the top of the screen
 - The notebook should open, there are a series of cells, to execute the code in a cell use SHIFT+ENTER or click on the cell press the Play icon on the left. Some of the cells will take a while to execute as they install necessary software or download files.
 - If you execute each cell in order you should be able to follow the process of building the visualisation, there's a bit of code but you don't need to understand it all to try it out!
 - Towards the end, an inline window should appear in one of the cells that you can use to control the visualisation, use the left mouse button to rotate and the right to translate. Each action is executed in the browser first with just the bounding box of the 3D scene, then the updated image is rendered remotely on google's servers using the GPU and updated in your browser... so it's a little slower to get a response than if you are running it on your own hardware, but you can access it from anywhere and no software installation is necessary!
 - The output of these visualisations can be viewed in VR in the CAVE2 and 

## Demonstrations (VR)
Mushroom : loading data sets imported using the Previs tools.
- Point cloud data - from photogrammetry (3D scanning)
- Mesh models - Kookaburra, Plain of Jars

The Body VR : an example of a VR experience with high production values, beyond what we are introducing here but a great example of what can be achieved with serious development time and effort

WebVR - try out some demos in the new WebVR standard (experimental)
 - https://experiments.withgoogle.com/collection/webvr
 - https://aframe.io/
 - https://mixedreality.mozilla.org/mobile/
 - https://docs.microsoft.com/en-us/microsoft-edge/webvr/demos
 - https://accessmars.withgoogle.com/ (Currently down unfortunately while updated to WebXR, check back!)

## Follow up
Where to access VR equipment?
 - MIVP & Library
 - FIT @ Caulfield

Future workshops - what next? Requests? Vote on the etherpad!
 - More on general 3D vis techniques or concentrate on VR only?
 - Coding: Unity3D development
 - Coding: 3D visualisations with IPython
 - No coding required tutorials for specific types of research data, which data?
 - 3D scanning and model creation?
 - General data visualisation (2D plots etc)
 
Contacts... see etherpad



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQxMjU2OTY5MCw0NzUzMzY4MDBdfQ==
-->