<template>
  <div class="small">
    <line-chart v-if="dataTemp.length > 0" :width="width" :height="height" :chart-data="datacollection"></line-chart>
  </div>
</template>

<script>
  import LineChart from '../assets/javascript/LineChart.js'

  export default {
    components: {
      LineChart
    },
    data () {
      return {
        datacollection: null,
        width: 525,
        height: 285,
        dataTemp: [],
        semaineMeteo: []
      }
    },
    mounted () {
      this.getDay()
      this.getInfo()
      this.fillData(this.dataTemp, this.semaineMeteo)
    },
    methods: {
      getDay(){
        const semaine = ['lundi', 'mardi', 'mercredi', 'jeudi', 'vendredi', 'samedi' , 'dimanche']

        const dateOfToday = new Date()
        // console.log(dateOfToday.getDay())
        let keyDay = dateOfToday.getDay() - 1
        console.log(keyDay)
        for(let i = keyDay ; i <= 6 ; i++){
          this.semaineMeteo.push(semaine[i])
          if(i === 6){
            for(let j = 0 ; j <= keyDay - 1 ; j++){
              this.semaineMeteo.push(semaine[j])
            }
          }
        }
        return this.semaineMeteo

      },
      getInfo(){
        fetch('https://api.openweathermap.org/data/2.5/onecall?lat=33.441792&lon=-94.037689&%20exclude=hourly,daily&appid=d578d6888b57e79f878b7d5bf8517065')
      .then(response => response.json())
      .then((data) => {
        data.daily.forEach((day) => {
          this.dataTemp.push((day.temp.day) - 273.15)
        })
      })
      .catch((err) => {
        console.log(err)
      })
      },
      fillData (temp, semaine) {
        console.log(temp)
        const colors = ['#007bff','#28a745','#333333','#c3e6cb','#dc3545','#6c757d'];
        this.datacollection = {
          labels: semaine,
          datasets: [
          {
            data: temp,
            backgroundColor: colors[3],
            borderColor: colors[1],
            borderWidth: 4,
            pointBackgroundColor: colors[1]
          }]
        }
      },
      getRandomInt () {
        return Math.floor(Math.random() * (50 - 5 + 1)) + 5
      }
    }
  }
</script>

<style>

</style>
