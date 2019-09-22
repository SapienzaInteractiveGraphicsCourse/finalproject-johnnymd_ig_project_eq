# Interactive Graphics  -  Final Project  -  2019  -  [Web Demo](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/)

>   La Sapienza - University of Rome



[TOC]

## Project requirements:

### - The Project Manager

>   <u>**REQUIREMENTS**</u>: **Can be done in groups of 1 to 4 persons.**

One person (just me).



### - The Story  -  The Project Theme

This project consists in building an **Audio Visualizer**, like thus of modern Media Players application, to be integrated in a music player build on top of the *[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)*. 

The idea have the roots deep in my childhood, when I was exploring the digital world on my first desktop computer, when I for the first time was looking through the visualizations of my media player, wandered and curious about how it works and how they build that. 

And here we are... Now I have (hope almost) all the ingredients to build a good one by myself. About the power, design and functionalities of the current audio standard for the web - Web Audio API - I read recently in some interesting articles on *[Medium](https://medium.com/)*. I wanted to build something that I could use in the future, something practical, not just a 3D visualization. So, the intent was to create a web audio player running on the browser (nowadays almost all the computers have a browser) , a good one, where you can easily **drag and play** your music enjoying the nice visualization born in your mind and created with passion. 

Ok... that was the dream. Now it’s true ! 

[Enjoy the music](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/ )  !



>   There are already some tracks, uploaded by default for my personal library. Hope you will appreciate the default playlist. Anyway, you can **drag and drop** your own music files (even folders in the Chrome browser) to be played immediately.



### - Used libraries

>   <u>**REQUIREMENTS**</u>: **You can use «basic» WebGL or advanced libraries, such as [ThreeJS](http://threejs.org/) or [Babylon](http://babylonjs.com/) or others (in this case they must be approved).**

The project is based on  **[ThreeJS](http://threejs.org/)**  JavaScript 3D library (with a default WebGL renderer).

The project also make use of other additional JavaScript libraries, like:

-   [Stats.JS](https://github.com/mrdoob/stats.js/)  -  Performance Monitor for JavaScript  ( *FPS* - # of rendered frames in the last second,  *MS* - time for one frame rendering, *MB* - allocated memory );
-   [dat.GUI](https://github.com/dataarts/dat.gui)  -  Lightweight controller library for JavaScript. Used for the application’s GUI Control Panel design;
-   [Wavesurfer.JS](https://wavesurfer-js.org/)  -  a customizable audio waveform visualization, built on top of [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) and [HTML5 Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API). Used for the <u>HTML5 audio player</u> core design and functionalities;
-   [id3.js](https://github.com/43081j/id3)  -  Javascript ID3 tag parser for audio files. Used by the <u>HTML5 audio player</u> to get the audio files metadata;



### - Models use Policy

>   **<u>REQUIREMENTS</u>**: **You can use models created with a modeler or found online. YOU CANNOT IMPORT ANIMATIONS**.

NO models or animations was imported in this project.



### - Project Content

#### <u>--- **Hierarchical models** ---</u>

>   <u>**REQUIREMENTS**</u>: **Must include at least one <u>and</u> more complex of the model used in *<u>homework2</u>***.

Main objects included in the Project:


  -   *The Main Sphere* hierarchical object (*one sphere + one cube per sphere face + set of lines (original design approach) + 2 smaller spheres with alpha textures*);

  -   A set of particular *Particle Systems* with different properties that are composing the environment  where *The Main Sphere* is immersed (background); 



#### <u>--- **Lights and Textures** ---</u>

>   **<u>REQUIREMENTS</u>**: **At least one light, textures of different kinds (*color*, *normal*, *specular*, ... )**:

*The Main Sphere* and the set of *Cubes* on it are created with a  `THREE.MeshNormalMaterial()`   (using the `SphereGeometry()`  and  `BoxGeometry()`  *Three.JS*  geometries).

*The Particle Systems* are created as `THREE.Points()` objects with the `THREE.PointsMaterial()` . The single points are firstly created as `THREE.Vector3()` objects and added as vertices to a simple `THREE.Geometry()` (as many as the number of *The Particles Systems*).

*The Spiral Spheres* are two almost identical meshes created from two sphere geometries with an **alpha texture** (particular *alphaMap* settings ), animated by changing the texture offsets, are added to *The Main Sphere* hierarchical object with a **Point Light** inside each (*DoubleSide* *Rendering*  -  `THREE.MeshStandardMaterial()`) .

*The Wave Lines* (***time domain representation of the signal***) are generated  (and updated at render time) starting from the *Time Domain Data* array updated continuously by the *Analyser Node* of the *Web Audio API*...



#### <u>--- **User Interaction** ---</u>

>   **<u>REQUIREMENTS</u>**: **Depends on your theme, as an example: *turn on/off lights*, *change viewpoint*, *configure colors*, *change difficulty*,** . . . 

-   The Project have Control Panel GUI, where some of the objects’ properties could be modified, observing the immediate feedback ( around 15 different actions just on the Control Panel GUI);

-   You can use your mouse and keyboard, the touchpad or touchscreen (depending on the device) to move the camera inside the scene;
    



#### <u>--- **Animations** ---</u>

>   **<u>REQUIREMENTS</u>**: **Most objects should be animated, in particular the hierarchical models should perform animations that exploit their structure. ANIMATIONS CANNOT BE IMPORTED, should be implemented by you in javascript (WebGL, ThreeJS or other approved library)**.

 - NO imported animations;
 - The Particle Systems, each centered in the origin of *The Main Sphere*, performs simple smooth rotations;
 - Actions on different components of the hierarchical structure of *The Main Sphere* are performed in synchrony with the *audio dynamics* from the audio data obtained from the [Analyser Node](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode) of the Web Audio API audio context. The animation of this components are performed from different combinations of such actions (detailed explanation following bellow).





## Technical Details

### The Audio Player

The Audio Player of the project is based on and inspired by a  *[Wavesurfer.JS](https://wavesurfer-js.org/)*  demo example that I adapted for my project. I chose this library because it’s build on top of the  *[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)*  that I needed for the visualization part of the project.

The things I changed respect to the original demo consists in:

-   Restyling some of the player components (see `style/player-style/style.css`);
-   Added some extra functionalities to the player:
    1.  function createDefaultPlaylist






>   [Web Demo ](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/)

