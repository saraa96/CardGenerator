<template>
<h3>اسم الموظف</h3>
<input :value="formData.empName"
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