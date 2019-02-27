
# 3D and Virtual Reality data visualisation for researchers

Questions from run-through:

How do I do this with my data?
-   LavaVu : from IPython (demo?)
-   Mushroom : from PreVis (points/mesh/volume - more detail on how to generate accepted data types, examples)

Access to VR equipment? Library, MIVP, FIT @ Caulfield
Links to software / tools / videos
Links to example datasets
Activity - more interaction ? 3D reconstruction in real time - apps?
PreVis - demo account for wider access for anyone running workshops? (Ask Toan)

#### Activity Overview
There is growing interest in the use of virtual reality (VR) for research. The immersive spatial environment offered by VR offers new ways to gather and draw insights from research data. 
More broadly, 3D visualisation is useful for understanding complex data, and can be used to explore and share data visualisations on mobile devices and the web. 
This hands-on workshop will introduce participants to the equipment, software and processes involved in using 3D and VR to visualise research data. 
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
 - Prior skills ? None, 
 - Pre-reading : optional, see links below
 - Equipment: provided, but bring own laptop
 - 
#### Links
re-workshop reading?
 - https://medium.com/@KristianBouw/the-comprehensive-guide-to-getting-started-in-virtual-reality-c6a6419cf8cf
 - https://parameters.ssrc.org/2018/07/knowledge-in-3d-how-3d-data-visualization-is-reshaping-our-world/
 - https://serialmentor.com/dataviz/ "Fundamentals of Data Visualization" 

isualisations:
- 3D network : https://bl.ocks.org/vasturiano/972ca4f3e8e074dacf14d7071aad8ef9
- Anatomical : http://cave2.github.io/websurfer/?model=examples/quayle_kookaburra 
 - PreVis point cloud https://mivp-dws1.erc.monash.edu:3000/pointviewer/?tag=335663
Data sources:
- Terrain (Aus) http://elevation.fsdf.org.au/
- SkyMap: https://opensky-network.org/
- 3D Scanning : https://www.agisoft.com/ https://play.google.com/store/search?q=3d%20scanner 

## Intro:
### Definitions: Data Visualisation, 3D visualisation, Virtual Reality
- Data visualisation is a broader topic with increasing relevance to all research, and ties in particularly with the increased application of data science and machine learning to research data.
- 3D visualisation is a subset of data visualisation with a long history of use in science for visualising computational research data
- Virtual reality technology is a new way of engaging with these kinds of visual datasets for both analysis of data and outreach and communication of research data results

### Big Data?
Just like in industry, research data is increasing rapidly in volume, velocity, variety and veracity (ref), many researchers now have "big data" problems. Visualisation is one aspect of data science that can help comprehend even very large data sets.

(Data processing loop image)

(Example of visualisation of a large data set)

### At Monash?
At the Monash Immersive Visualisation Platform (MIVP) https://www.monash.edu/researchinfrastructure/mivp we are more oriented to the 3D vis and scientific vis side of things, but expanding our reach.
We maintain a number of high end visualisation facilities, including VR (headset and the room-scale CAVE2).
We also provide services creating 3D visualisations for researchers, from helping to create tools to analyse data visually to generating compelling visualisations for outreach and publication.

(Some Monash vis projects - MIVP)

The Faculty of IT is also heavily involved in visualisation and virtual reality, in various fields including data science research and the Human-Computer Interaction, Immersive Analytics (https://ialab.it.monash.edu/) and SensiLab (https://sensilab.monash.edu/) research groups.
Mostly based at the Caulfield campus, they have a lot of VR equipment and research projects across IT and the Arts 

(Some Monash vis projects - FIT)

TODO: Examples of Vis & VR projects...at Monash and elsewhere... VR in research

## Why 3D visualisation?

3D vis, or scientific visualisation is a subset of Data Visualisation - the communication of data by visual means.
I'm mostly going to talk about 3D Visualisation as this is a set of techniques that allows us to produce 3D renderings that can be used on both desktops, handhelds and virtual reality headsets.

 - Developed to represent 3D phenomena, eg: from instruments or simulations, with an emphasis on realistic rendering, perhaps with the addition of a time component (animation) (https://en.wikipedia.org/wiki/Scientific_visualization).  Think of recreating the experience of looking through a microscope, but for data generated by computers (simulations) or processed through computers (scanning techniques: instruments).
 - Data Visualisation methods and tools can also be applied (plots/graphs/relational maps etc).

(Sci-Vis image - eg, sim or volrend)

Using modern graphics processing hardware we can create an illusion of a 3D world or view to examine and analyse a model.
We have the video games industry to thank for the fast acceleration and widespread availability of these techniques which used to be only possible with extremely expensive specialist computing equipment.

We are still working with 2D images as the final output, all our displays are flat 2D planes:
 - 3D Vis requires translation to 2D Image from particular viewpoint from an infinite number of possible views and is impossible to encapsulate in a single image.

(Image of 3D Projection) 

This is one reason why research publications have been slow to adopt 3D visualisation, it does not work with traditional publication methods. There is increasing demand for interactive 3D in publication and it is changing: https://peerj.com/articles/355/#3Dvisualisation http://cave2.github.io/websurfer/?model=examples/quayle_kookaburra
(NOTE: FigShare also supports 3D models with inline WebGL viewer)

(Image of 3D model in publication)

One way to think about visualisations is to classify them into "realistic" and "abstract" plots.
 - In 2D the most basic realistic plot is a photograph, but also simpler cartoon style drawings, maps for example - basically, attempting to convey an image like one would expect to see with one's eyes. In 3D this type of plot attempts to construct a realistic 3D world / view and is by far the more heavily used technique.

(Example images)

 - Abstract: graphs etc provide heavily stylised ways of representing data, by plotting on a set of axes or with links to relate data elements or groups to each other, these use familiar shapes and concepts to generate a mental model of the data without attempting to represent it in a visually realistic way. This is more heavily used in 2D, but you can still do this in 3D of course, the simplest example being a scatter plot on 3 axes. Most of what people think of as data visualisation, including interactive 2D plots falls into this category.

(Example images)

 - These two types of representation are often combined to good effect - for example, plotting cities as circles on a map (a realistic spatial visualisation) by representing the population with the size of the circle (abstract).

(Example images)

In 3D, especially VR you usually want to create at least a baseline of a real world environment to plot your abstract data, such as a room or even just a ground plane, so people viewing can orient themselves. Techniques used in 2D do not always translate well to 3D however, and VR is a new paradigm, so think creatively about how you want to work with your data in VR, sticking to methods designed for output to 2D will be limiting.

### Reasons we might want to visualise in 3D?
Some good reasons you might want to use 3D visuals:
 - The data is inherently 3D (eg: 3D models, scans, geospatial data that includes the height axis)
 - The data is abstract and difficult to condense to 2D or comprehend with a 2D plot
 - The data can be mapped to an inherently 3D dataset, eg: can be plotted on a geospatial 3d dataset to map to locations
 - For fun / outreach / increased impact : humans find 3D visualisations more compelling than flat 2D images.

### When not to use 3D?
For example, see this chapter in "Fundamentals of Data Visualization" [https://serialmentor.com/dataviz/no-3d.html](https://serialmentor.com/dataviz/no-3d.html) which basically suggests avoiding 3D altogether.
- If you can communicate your data clearly in a 2D plot
- If there adding a 3rd dimension actually helps comprehend the data better

## Virtual Reality

### Why/when to use Virtual Reality in particular?
 - Where Immersion in data and 360 view is more useful than an overview
 - When interaction with visualised data/objects using VR controls would be more intuitive than point & click / keyboard / touchscreen

VR can be used to interrogate data spatially and find features using our inherent ability to explore 3D spaces using visual sensory information.
As an extension of 3D visualisation, it can further increase the impact and absorption of information into memory.  ("People recall information better through virtual reality" https://www.sciencedaily.com/releases/2018/06/180613162613.htm)
VR environments can also be used to research how people react to simulated environments or situations (see: Psychology Researchers at King's College https://www.kcl.ac.uk/ioppn/depts/psychology/research/researchgroupings/vrrg/projects-at-the-virtual-reality-research-group.aspx).

Creating really compelling VR experiences requires more work than just getting your data up on the screens, though. Interaction with the data must be designed to work in the VR environment.

### Equipment Overview
- Room scale facilities : CAVE2 and other CAVE like systems - these provide an immersive VR experience in a room like environment, but are expensive to build and run and usually only available at research facilities.

(Image of CAVE2)

- Head mounted displays (HMD) : high end - HTC Vive, Oculus Rift, through to Google cardboard. The concept was invented a long time ago but the technology to make it work well just wasn't there until recently. Now much more accessible and very effective.

(Image of HMD)

Run down of Oculus controllers etc ?


### What tools can create a 3D visualisation from our data (and possibly view it in a VR device):

1) Use a visualisation library or tool that can create 3D plots or models - these usually create abstract plots of data or are tools designed for scientific visualisation work.
 - Libraries usually work within a given programming environment (Matlab, Python, R, Web)
   (Matplotlib, D3, Plotly, LavaVu)
- Desktop applications designed for visualisation provide an all-in-one environment (ParaView, VisIt, Drishti)
- Currently many of these 3D plotting tools do not produce output for VR, they are for desktop or handheld device viewing only.
- Moving forward more visualisation libraries will support VR output directly which could make things easier. WebVR is helping with this, allowing WebGL visual output to be rendered to head mounted VR devices.

2) Use our "Previs" web portal to upload a data set, and view it using our tools (Previs, Mushroom, LavaVu)
 - Easiest way to get started, and this is what we'll demonstrate today in the workshop.
 - These tools are a work in progress but are intended to make it easy to access VR techniques by researchers, by supporting common types of data that can be visualised.

3) Develop content using a framework that supports VR such as A-Frame, Unity3D, UnrealEngine
 - This is more likely to be done by a programmer who specialises in 3D graphics but these frameworks are getting easier to learn if you are interested and have the time to get really into it! A-Frame in particular is targeted at anyone who knows some basic web programming.

## Using Previs for visualising 3D data:

### What data can we use and how do we visualise it?

### 3D / 360 video content

The easiest way to generate VR headset content is to film using a 360 camera, if you have access to one of these you can create realistic visualisations in 3D and VR of any real location.
Of course there is no interactive control of the path, it's a passive experience with some interaction giving control of the viewpoint direction only.

But, if we want to view data that can be interacted with in more dimensions, to walk through, for example - then we need to create a 3D visualisation first...

### How to render a 3D scene: Turning a dataset into a 3D object

The first step in visualising data in 3D is to translate it into a data type that can be easily rendered into a 3D scene.
The three most widely used data types for this task are Points, Meshes and Volumes: 

#### Points 
The simplest kind of data to plot in 3D, require an X,Y,Z coordinate, plus some rendering parameters (size/colour/shading etc) (which can be tied to data or represent real colours)
 - LiDAR / Photogrammetry : Quick recreation of a real world scene or object from photographic footage or laser scans (AgiSoft PhotoScan, Phone based 3D scanning)
 - Points as data points : points can be used to show elements of more abstract data types or even represent moving objects

#### Meshes
Create the illusion of objects by drawing the surface only (via a connected "Mesh" of triangles)
Used as the basis for drawing more complex objects, from simple shapes (sphere, cube, arrow) to detailed 3D models (people, terrain, anything that has a surface)
 - Created in 3D modelling applications
 - Can be created from the real world via 3D scanning (to point cloud, then further processing to a mesh)
 - Can be extracted from Volume data (next...)

#### Volumes
Think stacks of 3D images : resulting in cubes of data points on a regular grid in 3D
 - Direct result of 3D image scans : microscopy, CT scans, MRI scans
 - 3D Simulations and numerical models
 - Can plot directly via Volume Rendering - slow but often very fine quality rendering or extract surface or point data for simpler plots (slices, isosurfaces)

There are further common data types we can plot too.
(Lines, Shapes, Vectors [Glyphs - Arrows etc], Tracers, Text)
These can all be combined to create more complex visualisations

## Demonstrations
[Previs](https://mivp-dws1.erc.monash.edu:3000/)
- Point cloud data - from spreadsheet?
- Mesh model - kookaburra

[LavaVu](https://github.com/okaluza/lavavu)
- Volume data? (TODO: No demo ready yet)
- Combining into more complex visualisations? - IPython with WebVR output via LavaVu

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NDc0MjUzODgsLTYyODg4MDAwMCwyNz
E5MTQzNzcsLTEzNDc0MDMyNDYsMTEyNjQwODY3OCwtMTMyOTIz
MTU4MSwxNzQ3MTM0MCwtOTkxMTA2Mzg5LDE4Mzg5ODE3MzBdfQ
==
-->