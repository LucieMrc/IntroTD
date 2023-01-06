# Intro_TD

## TouchDesigner ???

Touchdesigner is a visual programmation langage used to create multimedia interactive content in real time. It is mostly used by artists and programmers to create artwork, performances and installations.

Touchdesigner allow 2D and 3D production, including rendering and composing tools, video and audio inputs and outputs, multi-screens support, video mapping, animation, 3D engine, and programmation tools.

Programming in TD is based on the connexion between different nodes, which all have parameters controling their operations.

Uses : mapping, VJing, interaction spectacteur/son/environement-visuels

## Inputs and outputs

Inputs :
- sound
- MIDI controller
- OSC (from Augmenta, Arduino)
- etc

Outputs :
- real-time video (video-mapping, led-mapping, ...)
- datas
- etc

## What I do

<img src="images/Enregistrement de l’écran 2022-09-12 à 17.01.41.gif" width="488"/>

<img src="images/Enregistrement de l’écran 2022-09-15 à 13.33.10.gif" width="488"/>

<img src="images/Enregistrement de l’écran 2022-09-23 à 12.28.49.gif" width="488"/>

[@lucie.mrc](https://www.instagram.com/luciemrc/)

## People doing things

[Borischimp504](https://www.instagram.com/borischimp504/) - photogrammetry

<img src="images/Borischimp504.gif" width="488"/>

[B2bk](https://www.instagram.com/b2bk.fr/) - photogrammetry

<img src="images/b2bk.gif" width="488"/>

[Kaoru Tanaka](https://www.instagram.com/velvet_kaoru/) - generative visuals

<img src="images/kaoru.gif" width="488"/>

[Roelof Knol](https://www.instagram.com/roelofknol/) - interactive installations

<img src="images/roefnol.gif" width="488"/>

[No One's Image](https://www.instagram.com/noonesimg/) - generative visuals

<img src="images/noonesimg.gif" width="488"/>

[Karlskene](https://www.instagram.com/karlskene/) - generative visuals with laser and projection

<img src="images/karlskene.gif" width="488"/>

[Simon Alexander-Adams](https://www.instagram.com/polyhop/) - generative visuals

<img src="images/simonaa.gif" width="488"/>


## People doing youtube tutorials

[Bileam Tschepe](https://www.youtube.com/channel/UCONptu0J1PCrW9YfBtSdqjA)

[PPPANIK](https://www.youtube.com/channel/UCWBbakpo_cATqJy9Dzf9x4w)

[Noto the Talking Ball](https://www.youtube.com/@NotoTheTalkingBall)

[The Interactive & Immersive HQ](https://www.youtube.com/channel/UC-9DT8kpvykuBEQ2iVatWbA)

[Matthew Ragan](https://www.youtube.com/@raganmd)

[Pakita12](https://www.youtube.com/@paketa12)


# Understanding TouchDesigner

## Interface

Network in the middle, palette on the left (you can close it), parameters on the right.

<img src="images/screen2.png"/>

On top, differents little parameters of TD, layout etc, on the bottom, the timeline.

## Nodes

6 categories of nodes :
- COMP (Components), representing different types of controls and various nodes.
- TOP (Texture Operators), allowing operations on 2D images.
- CHOP (Channel Operators), used for animations and audio.
- SOP (Surface Operators), native 3D objects of TD, handling 3D points, polygones, and other 3D primitives.
- MAT (Materials), used to apply materials and shaders on 3D renders.
- DAT (Data Operators), used for texts, scripts and data arrays.

Each categories have a color, and you cannot connect nodes from different categories. To connect a CHOP to a TOP in your network for example, you can either use a CHOPToTop node or link the parameter you want in the CHOP to a parameter in the TOP. The link will then be a dotted line instead of a full line.

Each node can be customized with a multitude of parameters particular to each, and allow the link of parameters between differents nodes, and to get data from any part of the TD project.

<!--## Interactions-->

# Basic actions

## Feedback loop

The basic feedback loop network : one texture TOP, going to a `Feedback TOP`, going to a modifier TOP (level, blur, etc), going to `Composite TOP` with the texture TOP.

<img src="images/screen1.png"/>

In the parameters of the `Feedback TOP`, we drag and drop the `Composite TOP` in the Target TOP slot, to have the grey arrow link between the TOPs closing the loop.

In the parameters of the `Level TOP`, in the Post tab, we set the opacity to a lower value like 0.9, to decrease the opacity of the layers as they go through the feedback loop.

In the parameters of the `Composite TOP`, we chose a operation mode like Add, or Atop.

My tutorial about [using the Feedback TOP](https://github.com/LucieMrc/TD_feedback_love).

## Exports
To export a .mov video : create a `Movie File Out` TOP at the very end of your network, chose a name and a place for the file in the file slot. To start a recording, activate the Record button in the parameters, and deactivite the Record button to stop the recording.

To send the video on a media server, create a `Syphon/Spout Out` TOP at the very end of the network.

## Audio-reactive

Create an `Audio File in` CHOP, in the parameters you can active Mono to have one channel instead of a stereo sound.

You can put your own sound or keep the example one from TD. 

Link it to a `Math` CHOP, go to the tab Range, change the From Range, I put -0.7 and 0.7 because it's the range I see on my CHOP. 

Then change the To Range, I put 0.2 and 0.3 because it looked best.

Click on the little cross on the bottom left of the node to activate the active viewer.

Create a `Circle TOP`, in the parameters Radius X and Y, drag and drop the chan1 from the `Math TOP`, and select CHOP Reference in the slot.

![screen de TD](./images/screen3.png)

![screen de TD](./images/screen4.png)

## Geometry

To create a basic 3D geometry network, you need 5 nodes.
- a SOP of your choice
- a `Geometry COMP`
- a `Camera COMP`
- a `Light COMP`
- a `Render TOP`
- a MAT of your choice

![screen de TD](./images/screen5.png)

You start by creating a SOP of your choice, here a `Sphere SOP`. 

Create a `Geomtry COMP` by dragging directly the out link of the Sphere and hitting tab.

The sphere should appear in the Geo. Create a `Camera COMP` and a `Light COMP`, then a `Render TOP`. Grey arrow links should appear between the three COMP and the render.

Then create a MAT of your choice, here a `Phong MAT`, and drag it on the `Geometry COMP`, and select Parm: Material.

# To go further

- [Audioreactive visual in TD](https://github.com/LucieMrc/TD_audioreact_love)

- [Using Kantan for video-mapping in TD](https://github.com/LucieMrc/TD_KantanMapper)

- [Photogrammetry in TD](https://github.com/LucieMrc/Photogrammetrie)

- [Using Augmenta with TD](https://github.com/LucieMrc/TD_Augmenta)