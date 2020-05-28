<template>
  <div class="small">
    <bar-chart :width="width" :height="height" :chart-data="datacollection" v-bind:class="{ 'side-bar-off': isClose }"></bar-chart>
  </div>
</template>

<script>
  import BarChart from '../assets/javascript/BarChart.js'
  import {bus} from '../main'
  export default {
    name: 'graph1',
    components: {
      BarChart
    },
    data () {
      return {
        datacollection: null,
        width: 525,
        height: 285,
        isClose: false
      }
    },
    mounted () {
      this.fillData()
       bus.$on('state', () => {
        this.isClose = !this.isClose

      })
    },
    methods: {
      fillData () {
        this.datacollection = {
          labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
          datasets: [
            {
              label: 'Data One',
              backgroundColor: [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1,
              data: [this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt(), this.getRandomInt()]
            }
          ]
        }
      },
      getRandomInt () {
        return Math.floor(Math.random() * (50 - 5 + 1)) + 5
      }
    }
  }
</script>

<style scope>
.side-bar-off{
  width: 700px;
}
</style>
