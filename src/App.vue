<template >
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div id= "app" class="bg">
  <Header :title="title" />
    <div id="inner-page" class="container mt-5 mb-5  shadow-lg bg-white border border-1 rounded">


    <div class="row mt-5 mb-5">


      <div class="col-xs-12 col-sm-12 col-md-6 col-lg-6  mt-2 mb-2 orange" >
        <UserInput
            :formData="formData"
            @ChangeFormData="ChangeFormData($event)"
        />
      </div>


      <div class="col-xs-12 col-sm-12 col-md-6 col-lg-6  mt-2 mb-2 border-end baige">
<GentreatedCard :empName="formData.empName" />
      </div>







    </div>
  </div>
  </div>


</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import UserInput from './components/UserInput.vue'
import GentreatedCard from './components/GentreatedCard.vue'
export default {
  name: 'App',
  components: {
    Header,
    UserInput,
    GentreatedCard
  },
  data(){
    return{
      title:"هيئة تطوير محمية الملك سلمان بن عبدالعزيز الملكية",
      formData:{
        empName:""
      }
    };
  },
  methods:{
    ChangeFormData(empName){
      console.log(empName)
      this.formData = Object.assign({},this.formData,empName)
    }
  }
}
</script>

<style>
#app {
 
  font-family:  'Tajawal', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
    height: 100%;
  margin: 0;
  /* color: #2c3e50; */
  /* margin-top: 60px; */
}
/* .bg{
 background-image: url(./assets/bg-1.jpg);
   height: 100%;

 Center and scale the image nicely 
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
} */




#inner-page{
  background-color: #d1ccbd !important;
}



</style>
