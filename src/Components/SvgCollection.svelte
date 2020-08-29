<script>
  import SvgCard from "../UI/SvgCard.svelte";
  export let fileList;
</script>

<style lang="scss"></style>

<div class="container _flex">
  {#each fileList as { fileName, preview }}
    <p>{fileName}</p>
    <SvgCard {fileName} {preview} />
  {/each}
</div>
