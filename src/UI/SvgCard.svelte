<script>
  export let fileName;
  export let selectedColor;
  // export let content;
  // export let width;
  // export let height;
  export let fileSize;
  export let preview;

  function changeBgColor(color) {
    color == "black" ? (selectedColor = "#000") : (selectedColor = "#fff");
  }
</script>

<style lang="scss">
  .container {
    margin-right: 15px;
    border-radius: 5px;
    .preview {
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
      position: relative;
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
    .colors {
      margin: 5px 0 0 5px;
      position: absolute;
      .common {
        width: 30px;
        height: 30px;
        border-radius: 50%;
        cursor: pointer;
      }
      .black {
        background: #000;
        margin-right: 5px;
      }
      .white {
        background: #fff;
      }
    }
  }
</style>

<div class="container">
  <div class="colors _flex">
    <div
      class="black common"
      on:click|preventDefault={() => changeBgColor('black')} />
    <div
      class="white common"
      on:click|preventDefault={() => changeBgColor('white')} />
  </div>
  <div class="preview" style="background : {selectedColor}">
    <img src={preview} alt={fileName} />
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
