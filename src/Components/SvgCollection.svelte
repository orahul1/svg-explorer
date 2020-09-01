<script>
  import SvgCard from "../UI/SvgCard.svelte";
  import Masonry from "svelte-masonry/Masonry.svelte";
  export let fileCollection;
  export let selectedColor;
</script>

<style lang="scss">
  .container {
    margin: 35px 0 0 20px;
  }
</style>

<div class="container">
  <Masonry gridGap={'0.75rem'}>
    {#each fileCollection as { fileName, fileSize, preview }}
      <SvgCard {fileName} {fileSize} {preview} {selectedColor}/>
    {/each}
  </Masonry>
</div>
