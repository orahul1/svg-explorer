<script>
  export let fileName;
  export let content;
  // export let width;
  // export let height;
  export let fileSize;
  export let preview;
</script>

<style lang="scss">
  .container {
    margin-right: 15px;
    border-radius: 5px;
    .preview {
      background: #fff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      border-top-left-radius: 5px;
      border-top-right-radius: 5px;
      padding: 10px;
      .content {
        text-align: center;
        &:focus {
          outline: none !important;
        }
      }
    }
    .details {
      background: rgb(43, 43, 43);
      color: #fff;
      padding: 15px;
      border-radius: 5px;
      p {
        margin: 0 0 10px 0;
      }
      .edit {
        cursor: pointer;
        padding: 7px 20px;
        border-radius: 5px;
        color: #fff;
        background: -webkit-linear-gradient(
          43deg,
          #41bbd0 0%,
          #507ac8 46%,
          #7970ff 100%
        );
        font-size: 1rem;
        font-weight: bold;
      }
    }
  }
</style>

<div class="container">
  <div class="preview">
  <img src="{preview}" alt="{fileName}">
    <!-- <div class="content" contenteditable="true" bind:innerHTML={content} /> -->
  </div>
  <div class="details">
    <p>File Name: {fileName}</p>
    <!-- <p>Width: {width}</p>
    <p>Height: {height}</p> -->
    <p>File Size : {fileSize}</p>
    <!-- <button class="edit">Edit</button> -->
  </div>
</div>
