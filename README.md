## Interactive Graphics  -  Final Project  -  2019  -  [Web Demo](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/)

>   La Sapienza - University of Rome

### Project requirements:

1. **Project theme (*personal choice*);** 

   > TODOS

   

2. **Can be done in groups of 1 to 4 persons;** 

   One person (just me).

   

3. **You can use «basic» WebGL or advanced libraries, such as [ThreeJS](http://threejs.org/) or [Babylon](http://babylonjs.com/) or others (in this case they must be approved);** 

   The project is based on **ThreeJS** JavaScript 3D library (with a default WebGL renderer).

   The project also make use of other additional JavaScript libraries, like:

   -   [Stats.JS](https://github.com/mrdoob/stats.js/)  -  Performance Monitor for JavaScript ;
   -   [dat.GUI](https://github.com/dataarts/dat.gui)  -  Lightweight controller library for JavaScript (used for the application’s Control Panel Design);
   -   [Wavesurfer.JS](https://wavesurfer-js.org/)  -  a customizable audio waveform visualization, built on top of [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) and [HTML5 Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) (used for the HTML5 audio player core design and functionalities);
   -   [id3.js](https://github.com/43081j/id3)  -  Javascript ID3 tag parser for audio files (used by the HTML5 audio player);

   

4. **You can use models created with a modeler or found online. YOU CANNOT IMPORT ANIMATIONS;** 

   NO models was imported in the project.

   

5. **The project MUST include:** 

   - **Hierarchical models:** 

     -   [x] At least one <u>and</u> more complex of the model used in *<u>homework2</u>*:

   
     -   *The Main Sphere* hierarchical object;
  -   A set of particular *Particle Systems* with different properties that are composing the environment  where *The Main Sphere* is immersed (background).
   
- **Lights and Textures:** 
  
  - At least one light, textures of different kinds (*color*, *normal*, *specular*, ... ):
  
       -   Two almost identical meshes created from two sphere geometries with an **alpha texture**, animated by changing the texture offsets are added to *The Main Sphere* hierarchical object with a **Point Light** inside each (*DoubleSide* *Rendering Material*) .
  
   - **User interaction:**  

     - Depends on your theme, as an example: *turn on/off lights*, *change viewpoint*, *configure colors*, *change difficulty*, ... :

       -   The Project have Control Panel GUI, where some of the objects’ properties could be modified, observing the immediate feedback ( around 15 different actions just on the Control Panel GUI);
  -   You can use your mouse and keyboard, the touchpad or touchscreen (depending on the device) to move the camera inside the scene;
      
  
- **Animations:** 
  
  - Most objects should be animated, in particular the hierarchical models should perform animations that exploit their structure. ANIMATIONS CANNOT BE IMPORTED, should be implemented by you in javascript (WebGL, ThreeJS or other approved library):
   - NO imported animations;
       - The Particle Systems, each centered in the origin of *The Main Sphere*, performs simple smooth rotations;
       - Actions on different components of the hierarchical structure of *The Main Sphere* are performed in synchrony with the *audio dynamics* from the audio data obtained from the [Analyser Node](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode) of the Web Audio API audio context. The animation of this components are performed from different combinations of such actions (detailed explanation following bellow).




>   [Web Demo](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/)

