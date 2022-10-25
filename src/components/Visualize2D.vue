<template>
  <div class="hello">
    <ScatterChart 
      :coordsData="coordsData()"
    />
    
    <p>トルク: <input v-model="torque" type="number"  :min=minTorque :max=maxTorque :step=stepTorque /></p>
    <p>
      <input v-model="torque" type="range" :min=minTorque :max=maxTorque :step=stepTorque />
    </p>
    
    <p>潜在変数1: <input v-model="firstLatent" type="number" :min=minLatent :max=maxLatent :step=stepLatent  /></p>
    <p>
      <input v-model="firstLatent" type="range" :min=minLatent :max=maxLatent :step=stepLatent />
    </p>

    <p>潜在変数2: <input v-model="secondLatent" type="number" :min=minLatent :max=maxLatent :step=stepLatent  /></p>
    <p>
      <input v-model="secondLatent" type="range" :min=minLatent :max=maxLatent :step=stepLatent />
    </p>
    
  </div>
</template>

<script>
import ScatterChart from '@/components/scatterChart'
import coords from '@/assets/coords.json'
export default {
  name: 'Visualize2D',
  components: {
    ScatterChart
  },
  data() {
    return {
      coords: coords,
      torque: "0.100",
      firstLatent: "0.00",
      secondLatent: "0.00",
      minTorque: "0.010",
      maxTorque: '0.180',
      stepTorque: '0.010',
      minLatent: "-1.00",
      maxLatent: '1.00',
      stepLatent: '0.20',
    }
  },
  methods: {
    coordsData() {
      var torque = Number(this.torque).toFixed(3)
      var firstLatent = Number(this.firstLatent).toFixed(2)
      var secondLatent = Number(this.secondLatent).toFixed(2)
      return this.coords[torque][firstLatent][secondLatent]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
