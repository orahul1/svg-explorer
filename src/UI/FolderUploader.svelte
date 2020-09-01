<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  /**
   * @description open file uploader when click on upload text
   */

  function openFolderUpload() {
    document.getElementById("folders").click();
  }

  function uploadFile($event) {
    dispatch("fileUpload", $event);
  }
</script>

<style lang="scss">
  .folders {
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
        #69d041 0%,
        #c8c050 46%,
        #f30707 100%
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    p {
      font-size: 3rem;
      font-weight: bold;
      background: -webkit-linear-gradient(
        43deg,
        #69d041 0%,
        #c8c050 46%,
        #f30707 100%
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
  }
</style>

<section class="folders" id="folders-area" on:click={openFolderUpload}>
  <input
    type="file"
    id="folders"
    on:change={uploadFile}
    webkitdirectory
    mozdirectory />
  <i class="fas fa-folder" />
  <p>Folder upload</p>
</section>
