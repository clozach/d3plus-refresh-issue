<script>
  import { onMount } from 'svelte';

  const rewrap = () => {
    d3plus.textwrap()
      .text(title)
      .container(d3.select("#circleResize"))
      .resize(true)
      .draw();
  }

  onMount(rewrap);

  export let x = 0;
  export let y = 0;
  export const radius = 73;
  export let title;
  let skyHeight;

  $: title, rewrap();

</script>

<style>
  svg {
    font-family: "Helvetica", "Arial", sans-serif;
    height: 90%;
    width: 100%;
    background: transparent;
  }

  .type {
    fill: #888;
    text-anchor: middle;
  }

  .shape {
    fill: red;
    stroke: black;
  }

  .invis {
    fill: transparent;
    stroke: transparent;
    stroke-width: .1rem;
  }

  .title {
    fill: #ffebeb;
  }
</style>

<svg transform="translate({x},{y})">
  <path id="Union" fill-rule="evenodd" clip-rule="evenodd" d="M146.231 88C141.59475 149.06325 110.55825 179.34275 78.1905 180.40625C78.71225 180.728 78.98625 181.101 78.85975 181.46825C78.7125 181.8955 78.34075 182.20475 77.83725 182.4085C78.45875 182.785 78.98675 183.0765 79.29625 183.13525C81.0825 183.47525 82.3105 184.2075 82.18 185.1845C81.65975 189.07425 71.359 189.71475 69.8115 186.12075C69.3575 185.06575 70.63625 184.1365 72.54625 183.555C72.969 183.4265 72.994 182.79575 72.984 182.119C72.17475 181.7635 71.567 181.26075 71.41575 180.64475C71.376 180.48325 71.40175 180.33825 71.482 180.20975C39.4925 177.29075 7.890225 146.05275 0.7310525 88C-5.866625 34.5 33.30225 0 73.481 0C113.65975 0 150.0085 38.25 146.231 88z" fill="#C80E0E"/>

  <circle class="shape invis" r="{radius - 0.08*radius}" cx="{radius}"></circle>

  <text id="circleResize" class="wrap title" x="0px" y="{radius/1.75}" font-size="2rem">
    {title}
  </text>

</svg>
