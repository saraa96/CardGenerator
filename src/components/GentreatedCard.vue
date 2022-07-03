<template>
<div class="card-area" id="card-area" >
   <img src="../assets/card.png" alt="" width="350" height="450" class="d-inline-block pt-n5">
   <div class="empName">
       {{ empName }}
   </div>
</div>
<div class="mt-4">
    <button type="button" class="btn btn-secondary btn-lg" @click="generateCard()">تــحميــل</button>
</div>
</template>
<script>
import html2canvas from 'html2canvas';
export default {
  name: 'GentreatedCard',
  props:{
    empName:String,
  },
   methods:{
      async generateCard() {
        const canvas = await html2canvas(document.getElementById("card-area"));
        canvas.style.display = "none";
        document.body.appendChild(canvas);
        const image = canvas.toDataURL("image/png").replace("image/png", "image/octet-stream");
        const a = document.createElement("a");
        a.setAttribute("download", `collegeidcard.png`);
        a.setAttribute("href", image);
        a.click();
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