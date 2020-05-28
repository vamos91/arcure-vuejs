<template>
  <div class="button center">
    {{ msg }}
  </div>
</template>

<script>
  export default{
    name: 'navlink',
    props:{
      msg: String
    }
  }
</script>

<style scope>
  .button{
    padding: 10px;
    border-radius: 5px;
    background-color: transparent;
    color: white;
    margin: 10px;
    font-size: 14px;
  }

  .button:hover{
    background-color: #494E53;
  }

  .center{
    display: flex;
    align-items: center;
  }
</style>
