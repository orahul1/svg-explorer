<script>
  export let fileName;
  // export let fileSize;
  export let preview;
  console.log(fileName, preview);
</script>



<div class="container">
  <p>from card</p>
  <!-- <div class="preview" contenteditable="true" bind:innerHTML={preview}/> -->
  <div class="details">
    <p>{fileName}</p>
    <!-- <p>{fileSize}</p> -->
  </div>
</div>
