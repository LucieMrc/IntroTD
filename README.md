# IntroTD

## TouchDesigner ???

Touchdesigner is a visual programmation langage used to create multimedia interactive content in real time. It is mostly used by artists and programmers to create artwork, performances and installations.

Touchdesigner allow 2D and 3D production, including rendering and composing tools, video and audio inputs and outputs, multi-screens support, video mapping, animation, 3D engine, and programmation tools.

Programming in TD is based on the connexion between different nodes, which all have parameters controling their operations.

Uses : mapping, VJing, interaction spectacteur/son/environement-visuels

## Inputs and outputs

Inputs :
- dound
- MIDI controler
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

