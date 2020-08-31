<script>
  import FileUploader from "./Components/FileUploader.svelte";
  import SvgCollection from "./Components/SvgCollection.svelte";
  let isShowUploader = true;
  let fileCollection = [{
  fileName: 'vehicle',
  content: `<svg xmlns="http://www.w3.org/2000/svg" width="55" height="35" viewBox="0 0 55 35">
  <metadata><?xpacket begin="ï»¿" id="W5M0MpCehiHzreSzNTczkc9d"?>
<x:xmpmeta xmlns:x="adobe:ns:meta/" x:xmptk="Adobe XMP Core 5.6-c138 79.159824, 2016/09/14-01:09:01        ">
   <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
      <rdf:Description rdf:about=""/>
   </rdf:RDF>
</x:xmpmeta>
<?xpacket end="w"?></metadata>
<defs>
    <style>
      .cls-1 {
        fill: #0f86be;
        fill-rule: evenodd;
      }
    </style>
  </defs>
  <path class="cls-1" d="M51.365,29.014H50.158a6.611,6.611,0,0,0-13.163,0H17.544a6.661,6.661,0,0,0-7.35-5.944,6.7,6.7,0,0,0-5.813,5.944H3.84A2.9,2.9,0,0,1,1,26.144V22.694a2.853,2.853,0,0,1,2.071-2.72l9.26-2.582A1.259,1.259,0,0,0,13,16.939l5.529-7.354A4.031,4.031,0,0,1,21.787,8H33.025C33.016,8.166,33,8.331,33,8.5a8.5,8.5,0,0,0,13.195,7.083l0.8,1.292a1.211,1.211,0,0,0,.536.464l4.92,2.307A2.765,2.765,0,0,1,54,22.206v3.939A2.737,2.737,0,0,1,51.365,29.014ZM41.423,15.181a6.73,6.73,0,1,1,6.765-6.729A6.755,6.755,0,0,1,41.423,15.181Zm2.756-7.726H42.425V5.709a1,1,0,0,0-2,0V7.454H38.667a1,1,0,1,0,0,1.994H40.42v1.745a1,1,0,0,0,2,0V9.448h1.754A1,1,0,1,0,44.179,7.454ZM10.962,25.5a4.25,4.25,0,1,1-4.155,4.249A4.2,4.2,0,0,1,10.962,25.5Zm32.615,0a4.2,4.2,0,0,1,4.155,4.249h0A4.156,4.156,0,1,1,43.577,25.5Z"/>
</svg>`,
fileSize: '44.kb',
},
{
fileName: 'column',
content: `<svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 40 40">
  <metadata><?xpacket begin="ï»¿" id="W5M0MpCehiHzreSzNTczkc9d"?>
<x:xmpmeta xmlns:x="adobe:ns:meta/" x:xmptk="Adobe XMP Core 5.6-c138 79.159824, 2016/09/14-01:09:01        ">
   <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
      <rdf:Description rdf:about=""/>
   </rdf:RDF>
</x:xmpmeta>
<?xpacket end="w"?></metadata>
<defs>
    <style>
      .cls-1 {
        fill: #0f86be;
        fill-rule: evenodd;
      }
    </style>
  </defs>
  <path id="Forma_1_copy_6" data-name="Forma 1 copy 6" class="cls-1" d="M29.711,38H32.74A2.481,2.481,0,0,0,35,35.357V3.643A2.481,2.481,0,0,0,32.74,1H29.711a2.481,2.481,0,0,0-2.26,2.643V35.357A2.482,2.482,0,0,0,29.711,38ZM18.516,38h2.968a2.474,2.474,0,0,0,2.239-2.643V3.643A2.474,2.474,0,0,0,21.483,1H18.516a2.474,2.474,0,0,0-2.239,2.643V35.357A2.474,2.474,0,0,0,18.516,38ZM7.26,38h3.029a2.481,2.481,0,0,0,2.26-2.643V3.643A2.481,2.481,0,0,0,10.289,1H7.26A2.481,2.481,0,0,0,5,3.643V35.357A2.481,2.481,0,0,0,7.26,38Z"/>
</svg>`,
fileSize: '44.kb',
},
{
fileName: 'edit',
content: `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20">
  <metadata><?xpacket begin="ï»¿" id="W5M0MpCehiHzreSzNTczkc9d"?>
<x:xmpmeta xmlns:x="adobe:ns:meta/" x:xmptk="Adobe XMP Core 5.6-c138 79.159824, 2016/09/14-01:09:01        ">
   <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
      <rdf:Description rdf:about=""/>
   </rdf:RDF>
</x:xmpmeta>
<?xpacket end="w"?></metadata>
<defs>
    <style>
      .cls-1 {
        fill: #474747;
        fill-rule: evenodd;
      }
    </style>
  </defs>
  <path id="Forma_1" data-name="Forma 1" class="cls-1" d="M14.321,9.5a0.536,0.536,0,0,0-.536.536v5.357a0.536,0.536,0,0,1-.536.536H3.607a0.536,0.536,0,0,1-.536-0.536V4.678a0.536,0.536,0,0,1,.536-0.536h6.429a0.536,0.536,0,0,0,0-1.071H3.607A1.607,1.607,0,0,0,2,4.678V15.393A1.607,1.607,0,0,0,3.607,17H13.25a1.607,1.607,0,0,0,1.607-1.607V10.035A0.536,0.536,0,0,0,14.321,9.5ZM16.4,2.6a2.05,2.05,0,0,0-2.9,0L6.443,9.657a0.54,0.54,0,0,0-.129.209L5.242,13.081a0.536,0.536,0,0,0,.508.705,0.546,0.546,0,0,0,.169-0.027l3.214-1.071a0.537,0.537,0,0,0,.21-0.13L16.4,5.5A2.051,2.051,0,0,0,16.4,2.6Z"/>
</svg>`,
fileSize: '44.kb'
}];
</script>


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
