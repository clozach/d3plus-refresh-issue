<svelte:window bind:innerWidth={windowWidth} bind:innerHeight={windowHeight}/>

<script>
  import Balloon from './Balloon.svelte';

  export let name;
  let x;
  let y;
  let windowWidth;
  let windowHeight;
  let scale;
  let radius;
  let minY = 150;
  let title = "Why is it so difficult to center text in a shape like this while specifying curved outer bounds?";``
</script>

<input style="width:100%" type="text" bind:value={title}>

<label>x
	<input type="range" bind:value={x} max={windowWidth - (2 * radius)}>
</label>

<label>y
	<input type="range" bind:value={y} max={windowHeight - (2 * minY)}>
</label>

<label>scale
	<input type="range" bind:value={scale} min=0.7 max=3 step=0.01>
</label>

<div>x: {x}, y: {y}, scale: {scale}</div>

<Balloon bind:x bind:y bind:scale bind:radius bind:title/>
