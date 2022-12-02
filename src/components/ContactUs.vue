<template>
    <div id="contact" class="header-text">Contact-us Component</div>
    <p id="name">Name :{{name}}</p>
    <input type="text" v-model="name">
  </template>
  
  <script>
  export default {
      name: 'ContactUs',
      data() {
        return{
            name:''
            
        }
      }
  }
  </script>
  
  <style scoped>
  .header-text{
  margin-top: 10px;
  font-size: 22px;
  color: orangered;
}
  </style>