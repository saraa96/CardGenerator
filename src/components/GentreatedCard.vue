<template>
<div class="card-area" id="card-area">
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
import domtoimage from "dom-to-image-more";
import copyImageToClipboard from "copy-image-clipboard"
import { saveAs } from 'file-saver';
import html2canvas from 'html2canvas';
export default {
  name: 'GentreatedCard',
  props:{
    empName:String,
  },
   methods:{


generate_card (){
//     console.log("CLIK")
// var card = html2canvas(document.getElementById("card-area"));
// card.style.display = "none"
// document.body.appendChild(card);
// const img = card.toDataURL("image/png").replace("image/png","image/octet-stream");
// const a = document.createElement("a");
// a.setAttribute("download","haj.png");
// a.setAttribute("href",img);
// a.click();

// var node = document.getElementById("card-area");

// domtoimage
//   .toPng(node)
//   .then(function (dataUrl) {
//     var img = new Image();
//     img.src = dataUrl;
//     document.body.appendChild(img);
//   })
//   .catch(function (error) {
//     console.error("oops, something went wrong!", error);
//   });


domtoimage.toBlob(document.getElementById("card-area"), {quality: 0.95, width:802, height: 1200}).then(function (blob) {
  window.saveAs(blob, "my-card.png");
});

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
position: absolute;
  top: 80%;
  /*left: 35%;*/
  width: 100%;

  color: #fff !important;
  /* transform: translate(-50%, -50%); */
}
</style>