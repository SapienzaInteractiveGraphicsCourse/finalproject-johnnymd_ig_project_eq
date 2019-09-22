# Interactive Graphics  -  Final Project  -  2019  -  [Web Demo](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/)

>   La Sapienza - University of Rome



[TOC]

## Project requirements:

### - The Project Manager

>   <u>**REQUIREMENTS**</u>: **Can be done in groups of 1 to 4 persons.**

One person (just me).



### - The Story  -  The Project Theme

This project consists in building a *[Three.JS](http://threejs.org/)*  based   **Audio Visualizer**,  like thus of modern Media Players application, to be integrated in a music player build on top of the *[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)*. 

The idea have the roots deep in my childhood, when I was exploring the digital world on my first desktop computer, when for the first time I was looking through the visualizations of my media player, wandered and curious about how it works and how they build that. 

And here we are... Now I have (hope almost) all the ingredients to build a good one, by myself. About the power, design and functionalities of the current audio standard for the web - *Web Audio API* - I had read recently in some interesting articles on *[Medium](https://medium.com/)*. I wanted to build something that I could use in the future, something practical, not just a 3D visualization. So, the intent was to create a web audio player running on the browser (nowadays almost all the computers have a browser) , a good one, where you can easily **drag and play** your music, enjoying the nice visualization born in your mind and created with passion. 

Ok... that was the dream. Now it’s true ! 

[Enjoy the music](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/ )  !



#### Supported Browsers

The project design was focused to run with good performance on **Chrome** browser, but have also good performance on other browsers.

During the development the project was tested and developed with the Chrome browser (sometimes tested also on Firefox browser) (`50-60 FPS`).

Final version tested successfully on both Chrome and Firefox browsers on local server.

Instead, online, on GitHub pages, we have dropdown in terms of FPS for the Firefox browser(`25-30 FPS`).

<u>SW Versions</u>: 

-   **Chrome** **77.0.3865.90 (64-bit)** (on Windows PC)  and  **Chrome 77.0.3865.92**  (64-bit)(on Android smartphone);

-   **Firefox 69.0.1 (64 bit)** (*Quantum*) (on Windows PC);

>   So, please, try it on Chrome browser for a better experience.



#### *Wiki How* of the player

![Help insights](img//Demo4__Controls_Updated.png)

>   There are already some tracks, uploaded by default for my personal library. Hope you will appreciate the default playlist. Anyway, you can **drag and drop** your own music files (even folders in the Chrome browser) to be played immediately.



#### *Wiki How* Control Panel GUI

Clicking on *Open Controls*, the Control Panel GUI will be displayed. You can play with some audio or lights parameters, change the *wave lines* colors or tune new dimensions for the cubes/bars around the *Main Sphere* and see the immediate result of your changes (select the **DefaultPreset** or **BetsPreset** to restore the default configurations).

Also if you are curious to see the view from infinity, click/tap on `ZOOM-OUT` button (switch it back to stay with the camera in the *good* *zone*).

In the <u>top-left corner</u> of the controls you can save and select the current configurations/values of the GUI controller. If, playing around with the controls, you found a interesting setup for you visualization - save it - or make screenshot. Also, I will be really happy to enjoy what you found. So, please share it with me. 

That’s actually haw I found, by case,  ***The RocketPreset***  that you can select from the menu (when some music is playing).



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



#### <u>--- **Lights, Textures and Materials** ---</u>

>   **<u>REQUIREMENTS</u>**: **At least one light, textures of different kinds (*color*, *normal*, *specular*, ... )**:

*The Main Sphere* and the set of *Cubes* on it are created with a  `THREE.MeshNormalMaterial()`   (using the `SphereGeometry()`  and  `BoxGeometry()`  *Three.JS*  geometries).

*The Particle Systems* are created as `THREE.Points()` objects with the `THREE.PointsMaterial()` . The single points are firstly created as `THREE.Vector3()` objects and added as vertices to a simple `THREE.Geometry()` (as many as the number of *The Particles Systems*).

*The Spiral Spheres* are two almost identical meshes created from two sphere geometries with an **alpha texture** (particular *alphaMap* settings ), animated by changing the texture offsets, are added to *The Main Sphere* hierarchical object with a **Point Light** inside each (*DoubleSide* *Rendering*  -  `THREE.MeshStandardMaterial()`) .



*The Wave Lines* (***time domain representation of the signal wave***) are generated  (and updated at render time) starting from the *Time Domain Data* array updated continuously by the *Analyser Node* of the *Web Audio API*. From this array is created a buffer with `THREE.Vector2()` points (we need just x-offset on the line and y-offset for the high), that is used to create `new THREE.SplineCurve()` that give us a smooth and round curve. For efficiency reasons the `SplineCurve` is not rendered, but we can sample a smaller set of points from it in order to create a simple `BasicMaterial` line with `THREE.Line()`. 



#### <u>--- **User Interaction** ---</u>

>   **<u>REQUIREMENTS</u>**: **Depends on your theme, as an example: *turn on/off lights*, *change viewpoint*, *configure colors*, *change difficulty*,** . . . 

-   The Project have a Control Panel GUI, where some of the objects’ properties could be modified, observing the immediate feedback ( around 15 different actions just on the Control Panel GUI);

- You can use your mouse and keyboard, the touchpad or touchscreen (depending on the device) to move the camera inside the scene;
- Obviously you can drag and drop in the project window new audio files to be played (even folders if on Chrome browser).



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

-   Added a new extra functionality to the player:

    -   The function  `createDefaultPlaylist(path, songs_list)`  which asynchronously loads the default songs list from the hosting server, making use of a `new XMLHttpRequest();` per file, was integrated in the player’s script (`Common/player_script.js  -  line 88`).

        ```javascript
        function createDefaultPlaylist(audio_path, songs_list) {
        	var len 		= songs_list.length;
        	for (var j = len - 1; j >= 0; j--) {
        		// Sound Url
        		var soundUrl = audio_path + songs_list[j];
        
        		// Create request to load the song from address
        		var request = new XMLHttpRequest();
        		request.open("GET", soundUrl, true);
        
        		// Obtain as a blob object
        		request.responseType = "blob";
        
        		// Send request and save it
        		request.onload = function(e){
        			if (this.status == 200) { 	// success
        				getID3Data(new Blob([this.response], {type: 'audio/mpeg'}),  function (song) {
        					allTracks.push(song);
        					playlist.push(song);
        				$('#list').append($(returnTrackHTML(song, playlist.length-1)));
        				});
        			}
        		};
        		// Send the XMLHttpRequest
        		request.send();
        	}
        }
        ```

        

    -   Note that the loading process of drag and drop of the files is much faster due to their local storing and processing;

-   HTML content was modified in order to make space for the visualization canvas;



##### The Web Audio API use

We make use of the [Analyser Node](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode) of the Web Audio API context. We get the node from the *Wavesurfer* object of the Player:

```javascript
	// Get the wavesurfer's analyser node object
	analyser 	= wavesurfer.backend.analyser;
```

 After we are interested to get the Time and Frequency Domain Data (javascript arrays):

 FFT (Fourier Fast Transform) algorithm is used to for the discrete Frequency Domain Data. 

Time Domain Data (tdd) comes directly from the *analyser* and `peaks`  array, used for the *Wave Lines*  <u>animation</u>, is updated consequently (`onAudioAvailable()`). So, on frame render time we can update the lines (see below *The Wave Lines* section).

```javascript
// 'audioprocess' event fires continuously as the audio plays. Also fires on seeking.
wavesurfer.on('audioprocess', function(e) {
    // update the 'fft' and 'tdd' arrays
	analyser.getByteFrequencyData(	fft  );
	analyser.getByteTimeDomainData(	tdd );

	// update the peaks array
	onAudioAvailable();
});

// 		.	.	.

// 'channelCountMode' is set to 'explicit' on an analyserNode,
// so we can get the correct # of channels of the AudioNode in input 
numChannels = analyser.channelCount;

// Set the FFT size (default fftSize=2048)(powers of 2)
//         (fft scale to one channel size)
analyser.fftSize = fftSize * numChannels;

// FFT time averaging (0 meaning no time averaging). The default value is 0.8;
analyser.smoothingTimeConstant = smoothingTimeConstantFFT; // set to 0.26 

// Initialize the buffers for the Frequency and Time Domain Data:
//     (it will be updated on 'onaudioprocess' event firing)
fft 		= new Uint8Array(analyser.frequencyBinCount);
tdd 		= new Uint8Array(analyser.fftSize);
```



### The Wave Lines

*The Wave Lines* (***time domain representation of the signal wave***) are generated  (and updated at render time) starting from the *Time Domain Data* array updated continuously by the *Analyser Node* of the *Web Audio API*. From this array is created a buffer with `THREE.Vector2()` points (we need just x-offset on the line and y-offset for the high), that is used to create `new THREE.SplineCurve()` that give us a smooth and round curve. For efficiency reasons the `SplineCurve` is not rendered, but we can sample a smaller set of points from it in order to create a simple `BasicMaterial` line. Much more efficient computationally.

```javascript
 	var delta_x		= (2*radius - 1.5 * radiusSS) / tdd_size * pickRate;
	// 			.	.	.
	// Build the SplineCurve
 	splineCurve = new THREE.SplineCurve( curvePoints );

	// Get enough points for the SplineCurve in order 
	// to build a smooth wave line (greater --> better --> costly)
	linePoints 	= splineCurve.getPoints( tdd_size * sampleRate );

	var waveGeometry = new 	THREE.BufferGeometry().setFromPoints( linePoints );
	var waveMaterial = new 	THREE.LineBasicMaterial({ color : waveColor });
	
	// Create the final object to add to the scene
	var wave = new THREE.Line( waveGeometry, waveMaterial );
	
	// after each line are rotated be an angle, uniformly over (2*PI) period
	// 			.	.	.
	wave.geometry.computeBoundingSphere();// need to be recomputed after the rotations
```






>   [Web Demo ](https://sapienzainteractivegraphicscourse.github.io/finalproject-johnnymd_ig_project_eq/)

