<template>
<h3>اسم الموظف</h3>
<input  type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" :value="formData.empName"
@input="ChangeFormData({empName:$event.target.value})"
placeholder="مثال:سارا خالد الحربي"
/>
</template>
<script>
export default {
  name: 'UserInput',
  props:{
    formData: Object,
  },
  methods:{
    ChangeFormData(value){
        console.log(value);
        this.$emit("changeFormData",value);
    },
  },
}
</script>


<style>
h3{
  color: #597163;
}

</style>