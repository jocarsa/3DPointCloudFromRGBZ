<?php session_start(); ?>
<html>
	<head>
	<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
		<title>Videojuego</title>
		<style>canvas { width: 100%; height: 100% }</style>
		<style>
			html, body {
				width: 100%;
				height: 100%;
			}

			body {
				background-color: #ffffff;
				margin: 0;
				overflow: hidden;
				font-family: arial;
			}

			#blocker {

				position: absolute;

				width: 100%;
				height: 100%;

				background-color: rgba(0,0,0,0.5);

			}

			#instructions {

				width: 100%;
				height: 100%;

				display: -webkit-box;
				display: -moz-box;
				display: box;

				-webkit-box-orient: horizontal;
				-moz-box-orient: horizontal;
				box-orient: horizontal;

				-webkit-box-pack: center;
				-moz-box-pack: center;
				box-pack: center;

				-webkit-box-align: center;
				-moz-box-align: center;
				box-align: center;

				color: #ffffff;
				text-align: center;

				cursor: pointer;

			}
			a{color:white;text-decoration:none;}
video{
	position:absolute;
	left:0px;
	right:0px;
	width:100%;
	z-index:1000;
}
		</style>
	</head>
	<body>	
		<!--<video autoplay>
			<source src="mp4/logo2.mp4"></source>
		</video>-->
		<script>
			
		</script>
		<script src="lib/jquery-1.11.1.min.js"></script>
		<script src="lib/three.min.js"></script>
		<script src="lib/Stats.js"></script>
		<script src="lib/CopyShader.js"></script>
		<script src="lib/OBJLoader.js"></script>
		<script src="lib/PointerLockControls.js"></script>
		<script src="lib/SSAOShader.js"></script>
		<script src="lib/AnaglyphEffect.js"></script>
		<script src="lib/EffectComposer.js"></script>
		<script src="lib/RenderPass.js"></script>
		<script src="lib/MaskPass.js"></script>
		<script src="lib/ShaderPass.js"></script>
		<div id="blocker">

			<div id="instructions">
				<span style="font-size:40px">Click to play</span>
				<br />
				(W, A, S, D = Move, SpaceBar = Jump, Mouse = Look, Esc = Exit)
				
				<br><label for="ssao">Ambient Occlusion:</label><input id="ssao" checked type="checkbox" onchange="updateOptions()"/><br />
				<br><label for="ssao">Stereo Vision:</label><input id="stereovision" checked type="checkbox" onchange="updateOptions()"/><br />
				
			</div>
			

		</div>
		<script>
			

			/*//////////////////CONDICIONES INICIALES///////////////*/
			var angulosol = 1;
			var effect;
			var camx,camz;
			var jugaobject = new THREE.Mesh;
			var rotx = 0;
			var camerax = 0;
			var camera, scene, renderer, composer;
			var depthScale = 0.5;
			var depthPassPlugin, depthTarget;
			var ssaoEffect, dotScreenEffect, rgbShiftEffect;
			function updateOptions() {
				ssaoEffect.enabled = document.getElementById('ssao').checked;
				dotScreenEffect.enabled = document.getElementById('dotScreen').checked;
				rgbShiftEffect.enabled = document.getElementById('rgbShift').checked;
			}
			function onWindowResize() {
				camera.aspect = window.innerWidth / window.innerHeight;
				camera.updateProjectionMatrix();
				renderer.setSize( window.innerWidth, window.innerHeight );
				depthTarget = new THREE.WebGLRenderTarget( window.innerWidth * depthScale, window.innerHeight * depthScale, { minFilter: THREE.LinearFilter, magFilter: THREE.LinearFilter } );
				depthPassPlugin.renderTarget = depthTarget;
				ssaoEffect.uniforms[ 'size' ].value.set( window.innerWidth * depthScale, window.innerHeight * depthScale );
				ssaoEffect.uniforms[ 'tDepth' ].value = depthTarget;
			}
			/*//////////////////CONDICIONES INICIALES///////////////*/
			$(document).ready(inicio)
			
			function inicio(){
			var instructions = document.getElementById( 'instructions' );
			/*//////////////////POINTERLOCK///////////////*/
			var havePointerLock = 'pointerLockElement' in document || 'mozPointerLockElement' in document || 'webkitPointerLockElement' in document;
			if ( havePointerLock ) {
				var element = document.body;
				var pointerlockchange = function ( event ) {
					if ( document.pointerLockElement === element || document.mozPointerLockElement === element || document.webkitPointerLockElement === element ) {
						controls.enabled = true;
						blocker.style.display = 'none';
					} else {
						controls.enabled = false;
						blocker.style.display = '-webkit-box';
						blocker.style.display = '-moz-box';
						blocker.style.display = 'box';
						instructions.style.display = '';
					}
				}
				var pointerlockerror = function ( event ) {
					instructions.style.display = '';
				}
				// Hook pointer lock state change events
				document.addEventListener( 'pointerlockchange', pointerlockchange, false );
				document.addEventListener( 'mozpointerlockchange', pointerlockchange, false );
				document.addEventListener( 'webkitpointerlockchange', pointerlockchange, false );
				document.addEventListener( 'pointerlockerror', pointerlockerror, false );
				document.addEventListener( 'mozpointerlockerror', pointerlockerror, false );
				document.addEventListener( 'webkitpointerlockerror', pointerlockerror, false );
				instructions.addEventListener( 'click', function ( event ) {
					instructions.style.display = 'none';
					// Ask the browser to lock the pointer
					element.requestPointerLock = element.requestPointerLock || element.mozRequestPointerLock || element.webkitRequestPointerLock;
					if ( /Firefox/i.test( navigator.userAgent ) ) {
						var fullscreenchange = function ( event ) {
							if ( document.fullscreenElement === element || document.mozFullscreenElement === element || document.mozFullScreenElement === element ) {
								document.removeEventListener( 'fullscreenchange', fullscreenchange );
								document.removeEventListener( 'mozfullscreenchange', fullscreenchange );
								element.requestPointerLock();
							}
						}
						document.addEventListener( 'fullscreenchange', fullscreenchange, false );
						document.addEventListener( 'mozfullscreenchange', fullscreenchange, false );
						element.requestFullscreen = element.requestFullscreen || element.mozRequestFullscreen || element.mozRequestFullScreen || element.webkitRequestFullscreen;
						element.requestFullscreen();
					} else {
						element.requestPointerLock();
					}
				}, false );
			} else {
				instructions.innerHTML = 'Your browser doesn\'t seem to support Pointer Lock API';
			}						
			/*//////////////////POINTERLOCK///////////////*/
			
			
			
						
			}
			
			var scene = new THREE.Scene();
			scene.fog = new THREE.Fog( 0xffffff, 1,1000 );
			var camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 2500);
			camera.position.y = 5
			var renderparameters = { antialias: false, alpha: false, clearColor: 0xFFFFFF };

			var renderer = new THREE.WebGLRenderer(renderparameters);
			effect = new THREE.AnaglyphEffect( renderer )
			effect.setSize(window.innerWidth, window.innerHeight);
			effect.outstretch = 2.0;
			renderer.setSize(window.innerWidth, window.innerHeight);
			
			renderer.shadowMapEnabled = true;
			renderer.shadowMapSoft = true;
			
			
			
			document.body.appendChild(renderer.domElement);

			
			      
			      /*//////////////////// JUGADOR //////////////////*/
			      /*
			      var texturajugador = THREE.ImageUtils.loadTexture( "jugador/persona.jpg" );		      
			            
			      	texturajugador.wrapS = THREE.RepeatWrapping; 
				texturajugador.wrapT = THREE.RepeatWrapping;				
				texturajugador.repeat.set( 1, 1 ); 				
			      	var materialjugador = new THREE.MeshLambertMaterial( { map: texturajugador } );
			        loader.load( 'jugador/persona.obj', function ( jugaobject ) {		        
			        	jugaobject.traverse( function ( child ) {
					        if (child instanceof THREE.Mesh) {					
					            child.material = materialjugador; 					
					        }
					    } );
					jugaobject.castShadow = true;
					jugaobject.receiveShadow = true;
					scene.add( jugaobject );
					jugaobject.rotation.x = -Math.PI/2;
					jugaobject.position.x += 1;
				} );
				*/
			      /*//////////////////// JUGADOR //////////////////*/

			 
			
			
			
			
			
			
			   
			
			/*//////////////////// LUCES //////////////////*/
				//Ahora creo una luz
			      // directional lighting
			      /*var directionalLight = new THREE.SpotLight(0xffffff);
			      //directionalLight.position.set(1, 1, 1).normalize();
			      //directionalLight.position.set(1, 1, 1);
			      directionalLight.position.x = -100;
      				directionalLight.position.y = 150;
      				directionalLight.intensity = 1;
			      directionalLight.castShadow = true;
			      directionalLight.shadowDarkness = 0.5;
			      directionalLight.shadowCameraVisible = true;
			     		directionalLight.shadowMapWidth = directionalLight.shadowMapHeight = 2048;	*/ 			     
			     // scene.add(directionalLight);
			      /*
			      var ambientLight = new THREE.AmbientLight(0x4c4c4c);
			      scene.add(ambientLight);
			      */
			     var light = new THREE.SpotLight(0xffffff);
			      //light.position.set(100, 100, 100);
			      light.position.x = 100;
			      light.position.y = 100;
			      light.position.z = 50;
			      light.castShadow = true;
				light.intensity = 1;
				light.shadowCameraNear = 1;
				light.shadowCameraFar = 250;
				//light.shadowCameraFov = 50;

				//light.shadowCameraVisible = true;

				light.shadowBias = 0.000001;
				light.shadowDarkness = 0.5;

				light.shadowMapWidth =  4096;
				 light.shadowMapHeight = 4096;
			
			      scene.add(light);
			      
			      var skyLight = new THREE.HemisphereLight(0x4c4c4c,0xcccccc,1);
			      scene.add(skyLight);
			/*//////////////////// LUCES //////////////////*/
			//
			// create the particle variables
			////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
geometry = new THREE.Geometry();

				
					

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
var colors = [];
var rojo = [];
var verde = [];
var azul = [];
var rojoz = [];
var alpha = [];
<?php
error_reporting(0);
			$radio = 0.1;
			$im = imagecreatefrompng("madridrgb.png");
			$imz = imagecreatefrompng("madridz.png");
			$contx = 1;
			$conty = 1;
			$contador = 0;
			$anchoenpixeles = 800;
			$altoenpixeles = 400;
				for($x = 0;$x < 3.1416*2 ;$x+=((3.1416*2)/$anchoenpixeles)){
					$contx = 1; 
					for($y = 0;$y< 3.1416;$y+=((3.1416)/$altoenpixeles)){
						$rgb = imagecolorat($im, $conty, $contx);
						$rgbz = imagecolorat($imz, $conty, $contx);
						$r = ($rgb >> 16) & 0xFF;
						$g = ($rgb >> 8) & 0xFF;
						$b = $rgb & 0xFF;
						$alpha = ($rgb & 0x7F000000) >> 24;
						$rz = ($rgbz >> 16) & 0xFF;
						$gz = ($rgbz >> 8) & 0xFF;
						$bz = $rgbz & 0xFF;
						echo 'rojo['.$contador.'] = '.$r.';';
						echo 'verde['.$contador.'] = '.$g.';';
						echo 'azul['.$contador.'] = '.$b.';';
						echo 'rojoz['.$contador.'] = '.($rz+30).';';
						echo 'alpha['.$contador.'] = '.($alpha).';';
						$contx++;
						$contador++;
					}
					$conty++;
				}
			?>
			var radio = 0.1;
			var iterador = 0;
			for(var x = 0;x < 3.1416*2 ;x+=((3.1416*2)/<?php echo $anchoenpixeles ?>)){
				for(var y = 0;y< 3.1416;y+=((3.1416)/<?php echo $altoenpixeles ?>)){
					
						var vertex = new THREE.Vector3();
						vertex.x = Math.sin(y)*Math.sin(x)*(radio*rojoz[iterador]+0)*3;
						vertex.y =  Math.cos(y)*(radio*rojoz[iterador])*1;
						vertex.z = (radio*rojoz[iterador]+0)*Math.sin(y)*Math.cos(x)*3;
						
						
							
							geometry.vertices.push( vertex );
							if(alpha[iterador] == 127){
								colors[iterador] = new THREE.Color( "rgb(0,0,0)" );
								
							}else{
							colors[iterador] = new THREE.Color( "rgb("+rojo[iterador]+","+verde[iterador]+","+azul[iterador]+")" );
							}
							iterador++;
							
							
					
				}
			}
			geometry.colors = colors;
			materials = new THREE.ParticleSystemMaterial( { size: 0.8, vertexColors: true   } );
			particles = new THREE.ParticleSystem( geometry, materials );
			scene.add( particles );
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
				//

			controls = new THREE.PointerLockControls( camera );
				scene.add( controls.getObject() );


			var render = function () {
				
				requestAnimationFrame(render);
				renderer.setClearColor( 0xffffff, 1 );
				
				
				renderer.autoClear = false;
				camera.position.z = 1;
				
				
				
				
				renderer.render(scene, camera );
				controls.update();
				
				
				
				angulosol += 0.00001;
				light.position.x = Math.cos(angulosol)*100;
				light.position.y = Math.sin(angulosol)*100;
				light.intensity = Math.sin(angulosol);
				
			};

			render();
		</script>
		
		<div id="ajax">
		</div>
		
		<!--<iframe src="musica/index.html" style="width:0px;height:0px;padding:0px;margin:0px;border:0px;">
		</iframe>-->
	</body>
</html>