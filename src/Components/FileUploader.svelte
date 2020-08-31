<script>
  import { createEventDispatcher } from "svelte";
  import FolderUploader from "../UI/FolderUploader.svelte";
  import MultipleFileUploader from "../UI/MultipleFileUploader.svelte";
  const dispatch = createEventDispatcher();
  const fileDetails = [];

  /**
   * @description Handling files emitted from file and folder upload
   * @param { event } upload event
   */
  function handleFileUpload(e) {
    let files = e.detail.target.files;
    for (let file of files) {
      const reader = new FileReader();
      reader.readAsBinaryString(file);
      reader.fileName = file.name;
      reader.onload = (event) => {
        const fileName = event.target.fileName;
        const content = event.currentTarget.result;
        const fileSize = fileSizeConverter(file);
        fileDetails.push({ fileName, content,fileSize });
        dispatch("fileList", fileDetails);
      };
    }
  }

  function fileSizeConverter(file) {
    var _size = file.size;
    var fSExt = new Array("Bytes", "KB", "MB", "GB"),
      i = 0;
    while (_size > 900) {
      _size /= 1024;
      i++;
    }
    var exactSize = Math.round(_size * 100) / 100 + " " + fSExt[i];
    return exactSize;
  }
</script>

<style lang="scss">

</style>

<section class="container _flex">
  <MultipleFileUploader on:fileUpload={handleFileUpload} />
  <FolderUploader on:fileUpload={handleFileUpload} />
</section>
