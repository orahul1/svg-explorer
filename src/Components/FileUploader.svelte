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
        const preview = event.currentTarget.result;
        fileDetails.push({ fileName, preview });
      };
    }
    dispatch("fileList", { data: fileDetails });
  }
</script>

<style lang="scss">

</style>

<section class="container _flex">
  <MultipleFileUploader on:fileUpload={handleFileUpload} />
  <FolderUploader on:fileUpload={handleFileUpload} />
</section>
