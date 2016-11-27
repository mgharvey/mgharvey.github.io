---
layout: page
permalink: /research/
title: Research
tagline: Michael G. Harvey
tags: [about, research, Michael G. Harvey]
modified: 5-20-14
comments: true
image:
  feature: siberia.jpg
---

***

I study the origins of avian diversity, primarily by examining populations in the early stages of speciation. Most of my research takes advantage of large comparative datasets, such as those that can be collected from natural history collections. I am always looking for new types of data and tools - currently, I use emerging technologies to obtain genetic data from across the genome and also examine morphological, ecological, and distributional data. Some examples of specific research projects are below. 
<br><br>

## Avian plumage evolution within and among species
***

<script src="js/three.js"></script>
		<script src="js/OrbitControls.js"></script>
		<script src="js/Detector.js"></script>
		<script src="js/OBJLoader.js"></script>
		<script src="js/MTLLoader.js"></script>
		<script>

			if ( ! Detector.webgl ) Detector.addGetWebGLMessage();

			var container, stats, controls;
			var camera, scene, renderer;

			var clock = new THREE.Clock();

			var mixers = [];

			init();

			function init() {

				container = document.createElement( 'div' );
				document.body.appendChild( container );

				//setting the camera setting, second parameter sets width and height

				camera = new THREE.PerspectiveCamera( 45, 500 / 300, 1, 2000 );

				// scene
				scene = new THREE.Scene();

				var ambient = new THREE.AmbientLight( 0xffffff, .6 );
				scene.add( ambient );

				var directionalLight = new THREE.DirectionalLight( 0xfff1f1, .5 );
				directionalLight.position.set( -1, .5, 1 );
				scene.add( directionalLight );

				var directionalLight2 = new THREE.DirectionalLight( 0xe6f2ff, .5);
				directionalLight2.position.set( 1, .75, -1 );
				scene.add( directionalLight2 );

				// // grid
				// var gridHelper = new THREE.GridHelper( 14, 1, 0xb0b0b0, 0xb0b0b0 );
				// gridHelper.position.set( 0, - 0.04, 0 );
				// scene.add( gridHelper );

				// texture

				var manager = new THREE.LoadingManager();
				manager.onProgress = function ( item, loaded, total ) {

					console.log( item, loaded, total );

				};

				var texture = new THREE.Texture();

				var onProgress = function ( xhr ) {
					if ( xhr.lengthComputable ) {
						var percentComplete = xhr.loaded / xhr.total * 100;
						console.log( Math.round(percentComplete, 2) + '% downloaded' );
					}
				};

				var onError = function ( xhr ) {
				};


				var mtlLoader = new THREE.MTLLoader();
				mtlLoader.setPath( 'obj/' );
				mtlLoader.load( 'example.mtl', function( materials ) {
					materials.preload();
					var objLoader = new THREE.OBJLoader();
					objLoader.setMaterials( materials );
					objLoader.setPath( 'obj/' );
					objLoader.load( 'example.obj', function ( object ) {
						object.position.y = 0;
						scene.add( object );
					}, onProgress, onError );
				});

				renderer = new THREE.WebGLRenderer();
				renderer.setPixelRatio( window.devicePixelRatio );
				renderer.setSize( 500, 300 );
				renderer.setClearColor( 0xd0d2d9 );

				container.appendChild( renderer.domElement );

				// controls, camera
				controls = new THREE.OrbitControls( camera, renderer.domElement );
				controls.target.set( 0, -2, 0 );
				camera.position.set( 10, 14, 5 );
				controls.update();

				animate();
			}


			function animate() {

				requestAnimationFrame( animate );

				if ( mixers.length > 0 ) {

					for ( var i = 0; i < mixers.length; i ++ ) {

						mixers[ i ].update( clock.getDelta() );

					}

				}

				render();

			}

			function render() {

				renderer.render( scene, camera );

			}

		</script>
<br><br>
**Main collaborators:** Dan Rabosky (UMich)
<br><br>
Birds have varied and spectacular plumages, but the source of this diversity is still largely unknown. Do plumage differences between species originate from variation within species? At what rates do different plumage characters, such as color or pattern, change through evolutionary time? I am addressing these questions by applying digital imagery and computer vision technologies to specimens housed at natural history collections. 
<br><br>

## Causes of population divergence
***

![structure!](/images/structure.png)
<br><br>
**Main collaborators:** Brian Tilston Smith (AMNH), Glenn Seeholzer (LSU), Haw Chuan Lim (USNM), Alex Aleixo (MPEG), Camila Ribas (INPA), Robb Brumfield (LSU)
<br><br>
Some species contain remarkable variation across their distributions, whereas others are similar from place to place. The extent to which these differences are random or are a result of differences among species in ecological or life history traits is largely unknown. I am examining trait dependence in geographic variation using population genetic data combined with ecological trait data. Comparative analyses of population genetic data allow us to examine the impact of species-specific traits on population divergence.
<br><br>
**Papers:** <a href="http://dx.doi.org/10.1101/085126" target="_blank">Harvey et al. in review</a>, Smith et al. in review, Lim et al. in review, <a href="http://mgharvey.github.io/docs/Smithetal2014b.pdf" target="_blank">Smith et al. 2014</a>
<br><br>

## Population-level patterns vs. macroevolution
***

![bamm!](/images/bamm.png)
<br><br>
**Main collaborators:** Brian Tilston Smith (AMNH), Glenn Seeholzer (LSU), Dan Rabosky (UMich), Robb Brumfield (LSU)
<br><br>
Although diversity within species varies widely, this variation may or may not persist over long evolutionary timescales to impact trends in species diversity. I combine population genetic data on intraspecific diversity with phylogenetic data on species diversity through time to assess links between diversity across timescales. If population-level patterns persist to macroevolutionary timescales, this supports the potential importance of processes at work within species in shaping organismal diversity across space and time. 
<br><br>
**Papers:** <a href="http://dx.doi.org/10.1101/085134" target="_blank">Harvey et al. in review</a>, Harvey and Rabosky in review
<br><br>

## The use of genomic data in systematics
***

![genomics!](/images/genomics.png)
<br><br>
**Main collaborators:** Brant Faircloth (LSU), Travis Glenn (UGA), Brian Tilston Smith (AMNH), John McCormack (Occidental), Robb Brumfield (LSU)
<br><br>
New DNA sequencing technologies are able to produce massive amounts of genetic data, but their application to research in systematics is in its infancy. I have been working to develop and test approaches for obtaining data appropriate for systematics. The method I have focused on is sequence capture of ultraconserved elements. <a href="http://www.ultraconserved.org" target="_blank">Ultraconserved elements</a> are parts of the genome shared by widely divergent species - this conservation facilitates alignment of homologous sequences and adjacent variable regions provide information for comparative study. I have also been working with sequence capture of other types of loci (such as exons) and with restriction digest associated DNA sequencing (RAD-Seq). I have been developing bioinformatics pipelines and analytical tools that allow these powerful genomic techniques to be brought to bear on non-model species and samples in museum collections.
<br><br>
**Papers:** <a href="http://mgharvey.github.io/docs/Harveyetal2016.pdf" target="_blank">Harvey et al. 2016</a>, <a href="http://mgharvey.github.io/docs/Smithetal2014.pdf" target="_blank">Smith et al. 2014</a>, <a href="http://mgharvey.github.io/docs/Fairclothetal2012.pdf" target="_blank">Faircloth et al. 2012</a>
