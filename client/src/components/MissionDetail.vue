<template lang="html">
  <div v-if="mission" id="missionDetail">
    <div id="detailWrapper">
      <h2>{{ mission.mission_name }}</h2>
      <div id="flexWrapper">
        <div id="left">
          <p>Mission Manufacturers : {{ mission.manufacturers }}</p>
          <p>Mission Payloads: {{ mission.payload_ids }}</p>
          <p>Mission Description {{ mission.description }}</p>
          <a :href="`${mission.website}`" target="_blank">For more information, click here.</a>



        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'mission-detail',
  data(){
    return {
      mission: null
    }
  },
  mounted(){
    eventBus.$on('selected-mission', (mission) => {
      this.mission = mission
    })
  }
}
</script>

<style lang="css" scoped>
#missionDetail{
  text-align: center;
  background-color: teal;
  border: 1px solid black;
  border-radius: 20px;
  padding: 20px;
  margin: 10px;
  align-items: center;
}
</style>
