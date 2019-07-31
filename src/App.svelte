<svelte:window bind:innerWidth={windowWidth} bind:innerHeight={windowHeight}/>

<script>
  import Balloon from './Balloon.svelte';

  export let name;
  let x;
  let y;
  let windowWidth;
  let windowHeight;
  let minX;
  let minY;
  let title = "Why is it so difficult to center text in a shape like this while specifying curved outer bounds?";``
</script>

<input style="width:100%" type="text" bind:value={title}>

<label>x
	<input type="range" bind:value={x} max={windowWidth - (2 * minX)}>
</label>

<label>y
	<input type="range" bind:value={y} max={windowHeight - (2 * minY)}>
</label>

<div>x: {x} y: {y}</div>

<Balloon bind:x bind:y bind:minX bind:minY bind:title/>
