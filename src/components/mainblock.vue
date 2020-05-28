<template>
  <div>
    <div class="thumb-data">
      <topthumb class="topthumb" title="test titre" nbItem="3" background="blue"></topthumb>
      <topthumb class="topthumb" title="test titre" nbItem="24" background="green"></topthumb>
      <topthumb class="topthumb" title="test titre" nbItem="18" background="yellow"></topthumb>
    </div>
    <div class="charts" >
      <graph1 class="card-chart"></graph1>
      <graph2 class="card-chart"></graph2>
    </div>


  </div>
</template>

<script>
  import topthumb from './topthumb'
  import graph1 from './Graph1'
  import graph2 from './Graph2'

  export default{
    name: 'mainblock',
    components:{
      topthumb,
      graph1,
      graph2
    }
  }
</script>

<style scope>

body{
  background-color: #F5F6F9;
}

.thumb-data{
  display: flex;
  align-items: center;
  justify-content: space-around;
  width: 100%;
  height: 22vh;
  margin: auto;
}

.topthumb{
  width: 30%;
}

.card-chart{
  background-color: white;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  padding: 10px;
  box-shadow: 0 0 1px rgba(0,0,0,.125), 0 1px 3px rgba(0,0,0,.2);
  margin-bottom: 15px;
}

.charts{
  display: flex;
  align-items: center;
  justify-content: space-around;
  /*width: 90%;
  margin: auto;*/


}
</style>
