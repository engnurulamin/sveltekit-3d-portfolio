<script lang="ts">
	import { T as Threlte } from '@threlte/core';
	import * as THREE from 'three';

	export let position: [number, number, number] = [0, 0, 0];
	export let geometry: THREE.BufferGeometry = new THREE.IcosahedronGeometry(3);
	export let rate = 0.5;

	const materialParams = [
		{ color: 0x2ecc71, roughness: 0 },
		{ color: 0xf1c40f, roughness: 0.4 },
		{ color: 0xe74c3c, roughness: 0.1 },
		{ color: 0x8e44ad, roughness: 0.1 },
		{ color: 0x1abc9c, roughness: 0.1 },
		{ color: 0x2980b9, roughness: 0, metalness: 0.5 },
		{ color: 0x2c3e50, roughness: 0.1, metalness: 0.5 }
	];
	const material = new THREE.MeshStandardMaterial({
		color: 'cornflowerblue',
		roughness: 0.1,
		metalness: 0.5
	});
</script>

<Threlte.Mesh {geometry} {material}></Threlte.Mesh>
