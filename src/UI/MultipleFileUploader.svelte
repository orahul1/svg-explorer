<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  /**
   * @description open file uploader when click on upload text
   */

  function openFileUpload() {
    document.getElementById("files").click();
  }

  function uploadFile($event) {
    dispatch("fileUpload", $event);
  }
</script>

<style lang="scss">
  .files {
    width: 50%;
    text-align: center;
    height: 95vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    cursor: pointer;
    input {
      display: none;
    }
    i {
      font-size: 5rem;
      cursor: pointer;
      background: -webkit-linear-gradient(
        43deg,
        #4158d0 0%,
        #c850c0 46%,
        #ffcc70 100%
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    p {
      font-size: 3rem;
      font-weight: bold;
      background: -webkit-linear-gradient(
        43deg,
        #4158d0 0%,
        #c850c0 46%,
        #ffcc70 100%
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
  }
</style>

<section class="files" id="files-area" on:click={openFileUpload}>
  <input type="file" id="files" on:change={uploadFile} accept=".svg" multiple />
  <i class="fas fa-images" />
  <p>Upload multiple files</p>
</section>
