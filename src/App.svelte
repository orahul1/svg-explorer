<script>
  import FileUploader from "./Components/FileUploader.svelte";
  import SvgCollection from "./Components/SvgCollection.svelte";
  import Footer from './Components/Footer.svelte';
  import Header from './Components/Header.svelte';
  let isShowUploader = true;
  let fileCollection = [];
</script>

<!-- Header -->
<Header/>

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
  <SvgCollection {fileCollection} />
{/if}


<!-- Footer -->
<Footer/>