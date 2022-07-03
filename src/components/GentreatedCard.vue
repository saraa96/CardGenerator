<template>
<div class="card-area" id="card-area" >
   <img src="../assets/card.png" alt="" width="350" height="450" class="d-inline-block pt-n5">
   <div class="empName">
       {{ empName }}
   </div>
</div>
<div class="mt-4">
    <button type="button" class="btn btn-secondary btn-lg" @click="generate_card()">تــحميــل</button>
</div>
</template>
<script>
// import domtoimage from 'dom-to-image';
import * as htmlToImage from 'html-to-image';
import { toPng, toJpeg, toBlob, toPixelData, toSvg } from 'html-to-image';
import domtoimage from "dom-to-image-more";
import copyImageToClipboard from "copy-image-clipboard"
import { saveAs } from 'file-saver';
import html2canvas from 'html2canvas';
// import * from 'downloadjs'
export default {
  name: 'GentreatedCard',
  props:{
    empName:String,
  },
   methods:{


generate_card (){
htmlToImage.toJpeg(document.getElementById('card-area'), { quality: 0.95 })
  .then(function (dataUrl) {
    var link = document.createElement('a');
    link.download = 'my-card.jpeg';
    link.href = dataUrl;
    link.click();
  });

//     htmlToImage.toPng(document.getElementById('card-area'), { quality: 10})
//   .then(function (dataUrl) {
//     download(dataUrl, 'my-node.png');
//   });




// domtoimage.toJpeg(document.getElementById("card-area"), { quality: 10})
//     .then(function (dataUrl) {
//         var link = document.createElement('a');
//         link.download = 'my-image-name.jpeg';
//         link.href = dataUrl;
//         link.click();
//     });
// domtoimage.toBlob(document.getElementById("card-area"), {quality: 0.95, width:802, height: 1200}).then(function (blob) {
//   window.saveAs(blob, "my-card.png");
// });

}




    
   }
   
}


</script>
<style>

.card-area{
  position: relative;
  text-align: center;
}
.empName{
font-family:  'Tajawal', sans-serif !important;
position: absolute;
  top: 80%;
  /*left: 35%;*/
  width: 100%;

  color: #fff !important;
  /* transform: translate(-50%, -50%); */
}
</style>