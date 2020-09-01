<script>
  import { createEventDispatcher } from "svelte";
  import { onMount } from 'svelte';
  const dispatch = createEventDispatcher();
  let selectedColor;
  export let showColors = false;

  function changeBgColor(color) {
    color == "black" ? (selectedColor = "#000") : (selectedColor = "#fff");
    dispatch("changeColor", selectedColor);
  }

  onMount(async () => {
    selectedColor = "#fff";
    dispatch("changeColor", selectedColor);
	});
</script>

<style lang="scss">
  .container {
    p {
      position: absolute;
      cursor: pointer;
      left: 0;
      font-size: 30px;
      background: -webkit-linear-gradient(
        43deg,
        #d0af41 0%,
        #76c850 46%,
        #70ff7c 100%
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    i {
      position: absolute;
      right: 0;
      margin-right: 15px;
      font-size: 2.5rem;
      cursor: pointer;
      background: -webkit-linear-gradient(
        43deg,
        #d0af41 0%,
        #76c850 46%,
        #70ff7c 100%
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .colors {
      position: absolute;
      right: 150px;
      .common {
        width: 30px;
        height: 30px;
        border-radius: 50%;
        cursor: pointer;
      }
      .black {
        background: #000;
        border: 0.5px solid #fff;
        margin-right: 5px;
      }
      .white {
        background: #fff;
        border: 1px solid #000;
        border: 0.5px solid #fff;
      }
    }
  }
</style>

<div class="container _flex">
  <p><a href="./">SVG-Explorer</a></p>
  {#if showColors}
    <div class="colors _flex">
      <div class="black common" on:click|preventDefault={() => changeBgColor('black')} />
      <div class="white common" on:click|preventDefault={() => changeBgColor('white')}/>
    </div>
  {/if}
  <a href="https://github.com/orahul1/svg-explorer" target="_blank">
    <i class="fab fa-github" /></a>
</div>
