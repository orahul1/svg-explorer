<script>
  import SvgCard from "../UI/SvgCard.svelte";
  import Masonry from "svelte-masonry/Masonry.svelte";
  export let fileCollection;
</script>

<style lang="scss">
  .container {
    margin: 35px 0 0 20px;
  }
</style>

<div class="container">
  <Masonry gridGap={'0.75rem'}>
    {#each fileCollection as { fileName, content, fileSize, preview }}
      <SvgCard {fileName} {content} {fileSize} {preview} />
    {/each}
  </Masonry>
</div>
