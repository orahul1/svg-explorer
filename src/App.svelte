<script>
  import FileUploader from "./Components/FileUploader.svelte";
  import SvgCollection from "./Components/SvgCollection.svelte";
  import Footer from './Components/Footer.svelte';
  import Header from './Components/Header.svelte';
  let isShowUploader = true;
  let selectedColor;
  let fileCollection = [];
</script>

<!-- Header -->
<Header showColors={!isShowUploader} on:changeColor={(data) => {selectedColor = data.detail}}/>

<!-- Fileuploaders -->

{#if isShowUploader}
  <FileUploader
    on:fileList={(data) => {
      fileCollection = data.detail;
      isShowUploader = false;
    }}/>
{/if}

<!-- SVG Collection -->

{#if !isShowUploader}
  <SvgCollection {fileCollection} {selectedColor}/>
{/if}


<!-- Footer -->
<Footer/>