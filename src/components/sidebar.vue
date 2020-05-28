<template>
  <div id="sidebar" class="sidebar-on" v-on:click="moveSideBar" v-bind:class="{ 'sidebar-off': sideBarState }">
    <ul class="sidebar-nav">
      <li><navlink msg="Global blaxtair data"></navlink></li>
      <li><navlink msg="Global detection data"></navlink></li>
      <li><navlink msg="Global detection chart"></navlink></li>
      <li><navlink msg="Global detection chart"></navlink></li>
    </ul>
  </div>

</template>

<script>
  import navlink from './navlink'
  import {bus} from '../main'
  export default{
    name: 'sidebar',
    components:{
      navlink
    },
    data(){
      return{
        sideBarState: false
      }
    },
    methods:{
      moveSideBar: function(){
        this.sideBarState = !this.sideBarState
        bus.$emit('state', this.sideBarState)
        console.log('state emit from sidebar component')
      }
    }
  }
</script>

<style scope>
#sidebar{
  background-color: #343A40;
  height: 100vh;
  color: white;
  display: flex;
  justify-content: center;
  border-right: 1px solid rgba(0, 0, 0, 0.2);
}

.sidebar-on{
  width: 300px;
  transition: 0.4s;
}

.sidebar-off{
  width: 50px;
  transition: 0.4s;
}

.sidebar-nav{
  margin-top: 100px;
  list-style: none;
}
</style>
