## Interactive Graphics  -  Final Project  -  2019  -  [Web Demo](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/)

>   La Sapienza - University of Rome



### Project requirements:

#### - The Project Manager

>   <u>**REQUIREMENTS**</u>: **Can be done in groups of 1 to 4 persons.**

One person (just me).



#### - The Story  -  Project theme

>   TO DO



#### - Used libraries

>   <u>**REQUIREMENTS**</u>: **You can use «basic» WebGL or advanced libraries, such as [ThreeJS](http://threejs.org/) or [Babylon](http://babylonjs.com/) or others (in this case they must be approved).**

The project is based on  **[ThreeJS](http://threejs.org/)**  JavaScript 3D library (with a default WebGL renderer).

The project also make use of other additional JavaScript libraries, like:

-   [Stats.JS](https://github.com/mrdoob/stats.js/)  -  Performance Monitor for JavaScript  ( *FPS* - # of rendered frames in the last second,  *MS* - time for one frame rendering, *MB* - allocated memory );
-   [dat.GUI](https://github.com/dataarts/dat.gui)  -  Lightweight controller library for JavaScript. Used for the application’s GUI Control Panel design;
-   [Wavesurfer.JS](https://wavesurfer-js.org/)  -  a customizable audio waveform visualization, built on top of [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) and [HTML5 Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API). Used for the <u>HTML5 audio player</u> core design and functionalities;
-   [id3.js](https://github.com/43081j/id3)  -  Javascript ID3 tag parser for audio files. Used by the <u>HTML5 audio player</u> to get the audio files metadata;



#### - Models use Policy

>   **<u>REQUIREMENTS</u>**: **You can use models created with a modeler or found online. YOU CANNOT IMPORT ANIMATIONS**.

NO models or animations was imported in this project.



#### - Project Content

##### <u>Hierarchical models</u>

>   **Must include at least one <u>and</u> more complex of the model used in *<u>homework2</u>***.

Main objects included in the Project:


  -   *The Main Sphere* hierarchical object (*one sphere + one cube per sphere face + set of lines (original design approach) + 2 smaller spheres with alpha textures*);

  -   A set of particular *Particle Systems* with different properties that are composing the environment  where *The Main Sphere* is immersed (background);
  -   A set of *Wave Lines* (**time domain representation of the signal**); 



##### <u>Lights and Textures</u>

>   **<u>REQUIREMENTS</u>**: **At least one light, textures of different kinds (*color*, *normal*, *specular*, ... )**:

*The Main Sphere* and the set of *Cubes* on it are created with a  `THREE.MeshNormalMaterial()`   (using the `SphereGeometry()`  and  `BoxGeometry()`  *Three.JS*  geometries).

*The Particle Systems* are created as `THREE.Points()` objects with the `THREE.PointsMaterial()` . The single points are firstly created as `THREE.Vector3()` objects and added as vertices to a simple `THREE.Geometry()` (as many as the number of *The Particles Systems*).

*The Spiral Spheres* are two almost identical meshes created from two sphere geometries with an **alpha texture** (particular *alphaMap* settings ), animated by changing the texture offsets, are added to *The Main Sphere* hierarchical object with a **Point Light** inside each (*DoubleSide* *Rendering*  -  `THREE.MeshStandardMaterial()`) .

*The Wave Lines* are generated (and regenerated at render time) starting from the *Time Domain Data* array updated continuously by the *Analyser Node* of the *Web Audio API*...



##### <u>User Interaction</u>

>   **<u>REQUIREMENTS</u>**: **Depends on your theme, as an example: *turn on/off lights*, *change viewpoint*, *configure colors*, *change difficulty*, ** . . . 

-   The Project have Control Panel GUI, where some of the objects’ properties could be modified, observing the immediate feedback ( around 15 different actions just on the Control Panel GUI);

-   You can use your mouse and keyboard, the touchpad or touchscreen (depending on the device) to move the camera inside the scene;
    



##### <u>Animations</u>

>   **<u>REQUIREMENTS</u>**: Most objects should be animated, in particular the hierarchical models should perform animations that exploit their structure. ANIMATIONS CANNOT BE IMPORTED, should be implemented by you in javascript (WebGL, ThreeJS or other approved library).

 - NO imported animations;
 - The Particle Systems, each centered in the origin of *The Main Sphere*, performs simple smooth rotations;
 - Actions on different components of the hierarchical structure of *The Main Sphere* are performed in synchrony with the *audio dynamics* from the audio data obtained from the [Analyser Node](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode) of the Web Audio API audio context. The animation of this components are performed from different combinations of such actions (detailed explanation following bellow).




>   [Web Demo ](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/)

