<script>
	export let id;
	import p5 from "../libs/p5.min";
	export let sketch;

	import { onMount } from "svelte";

	onMount(function() {
	  let myp5 = new p5(sketch, id);
	});
</script>

<style>
</style>

<div {id}></div>