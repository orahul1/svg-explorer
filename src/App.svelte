<script>
  import FileUploader from "./Components/FileUploader.svelte";
  import SvgCollection from "./Components/SvgCollection.svelte";
  let isShowUploader = true;
  let files = [];
</script>


<!-- Fileuploaders -->

{#if isShowUploader}
  <FileUploader
    on:fileList={(data) => {
      console.log(data)
      isShowUploader = false;
    }}/>
{/if}

<!-- SVG Collection -->

{#if !isShowUploader}
  <SvgCollection fileList={files} />
{/if}
