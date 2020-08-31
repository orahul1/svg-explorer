<script>
  import SvgCard from "../UI/SvgCard.svelte";
  import Masonry from "svelte-masonry/Masonry.svelte";
  export let fileCollection;
  console.log(fileCollection, "from svg collection com");
</script>

<style lang="scss">
  .container {
    margin: 20px 0 0 20px;
  }
</style>

<div class="container">
  <Masonry gridGap={'0.75rem'}>
    {#each fileCollection as { fileName, content, width, height, fileSize }}
      <SvgCard {fileName} {content} {fileSize}/>
    {/each}
  </Masonry>
</div>
