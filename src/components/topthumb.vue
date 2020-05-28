<template>
  <div class="top-thumb">
    <div class="stat-card" v-bind:class="background">
      <h2>{{ nbItem }}</h2>
      <p>{{ title }}</p>
      <i class="fas fa-car"></i>
    </div>
  </div>
</template>

<script>
  export default{
    name: 'topthumb',
    props:{
      title: String,
      nbItem: String,
      background: String
    }
  }
</script>

<style scope>
  .stat-card{
    position: relative;
    color: white;
    padding: 45px;
    border-radius: 5px;
    box-shadow: 0 0 1px rgba(0,0,0,.125), 0 1px 3px rgba(0,0,0,.2);
    margin-bottom: 15px;
  }

  .stat-card h2{
    font-weight: bold;
  }

  .stat-card .fa-car{
    position: absolute;
    right: 20px;
    font-size: 40px;
    top: 50px;
  }

  .blue{
    background-color: #18A2B8;
  }

  .green{
    background-color: #27A744;
  }

  .yellow{
    background-color: #FFC106;
  }
</style>
