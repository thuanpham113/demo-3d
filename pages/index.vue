<template>
	<div style="height: 100vh; width: 100vw; position: relative">
		<v-sheet height="100%" width="100%" class="pa-10" color="black" style="position: absolute">
			<instruction-player ref="player" border-radius="50px" src="/umbreon.glb" />
		</v-sheet>
		<div style="height: 100%; width: 100%; position: absolute" class="pointer-events-none">
			<div class="d-flex flex-column justify-center pointer-events-none" style="height: 100%;">
				<v-card height="50px" width="50px" color="red" class="ma-2 pointer-events-auto" @click="red">
					<!-- <v-color-picker
					v-model="c2"
					hide-inputs
					></v-color-picker>
					Choose color -->
				</v-card>
				<v-card height="50px" width="50px" color="green" class="ma-2 pointer-events-auto" @click="greeen" />
				<v-card height="50px" width="50px" color="#f1c232" class="ma-2 pointer-events-auto" @click="yellow" />
				<v-card height="50px" width="50px" color="white" class="ma-2 pointer-events-auto" @click="white" />
				<v-card height="50px" width="50px" color="black" class="ma-2 pointer-events-auto" @click="black" style="border: 2px solid white"/>
			</div>
		</div>
	</div>
</template>

<script>
import * as THREE from "three";
import { GLTFLoader } from "../node_modules/three/examples/jsm/loaders/GLTFLoader";
import { OrbitControls } from "../node_modules/three/examples/jsm/controls/OrbitControls.js";
import { TransformControls } from "../node_modules/three/examples/jsm/controls/TransformControls.js";
import { RoomEnvironment } from "../node_modules/three/examples/jsm/environments/RoomEnvironment.js";
export default {
	name: "IndexPage",
	data:()=>{
		return{

		}
	},
	methods: {
		red () {
			// this.$refs.dialogColor.dialog = true;
			const mesh = this.$refs.player.scene.getObjectByName(this.$refs.player.mesh);
			mesh.material.color.r = 1;
			mesh.material.color.g = 1;
			mesh.material.color.b = 1;
			mesh.material.envMapIntensity = 0;
			console.log(this.$refs.player.scene);
			console.log(mesh.material);
		},
		greeen () {
			const mesh = this.$refs.player.scene.getObjectByName(this.$refs.player.mesh);

			mesh.material.color.r = 1;
			mesh.material.color.g = 100;
			mesh.material.color.b = 5;
			mesh.material.envMapIntensity = 0;
		},
		white () {
			const mesh = this.$refs.player.scene.getObjectByName(this.$refs.player.mesh);

			mesh.material.color.r = 255;
			mesh.material.color.g = 255;
			mesh.material.color.b = 255;
			mesh.material.envMapIntensity = 0;
		},
		yellow () {
			const mesh = this.$refs.player.scene.getObjectByName(this.$refs.player.mesh);

			mesh.material.color.r = 100;
			mesh.material.color.g = 100;
			mesh.material.color.b = 1;
			mesh.material.envMapIntensity = 0;
		},
		black () {
			const mesh = this.$refs.player.scene.getObjectByName(this.$refs.player.mesh);

			mesh.material.color.r = 1;
			mesh.material.color.g = 1;
			mesh.material.color.b = 1;
			mesh.material.envMapIntensity = 0;
		},
		hoverObject(){

		},
		chooseObject(){

		}
	},
	mounted(){
		// const mousePosition = new THREE.Vector2();
		// const raycaster = new THREE.Raycaster();

		// let intersects;

		// window.addEventListener("mouseover", function(e){
			
		// 	raycaster.setFromCamera(mousePosition, THREE.Camera);
		// 	console.log(raycaster);
		// });
		// if(this.$refs.player.mesh != null){
		// 	const mesh = this.$refs.player.scene.getObjectByName(this.$refs.player.mesh);

		// 	// mesh.material.color = new THREE.Color( 0xff0000 )
		// }
	}
};
</script>

<style lang="scss">
html {
	overflow: hidden !important;
}
</style>