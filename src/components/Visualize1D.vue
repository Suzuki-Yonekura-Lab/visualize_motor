<template>
  <div class="hello">
    <ScatterChart 
      :coordsData="coordsData()"
    />
    
    <p>トルク: <input v-model="torque" type="number"  :min=minTorque :max=maxTorque :step=stepTorque /></p>
    <p>
      <input v-model="torque" type="range" :min=minTorque :max=maxTorque :step=stepTorque />
    </p>
    
    <p>潜在変数: <input v-model="latent" type="number" :min=minLatent :max=maxLatent :step=stepLatent  /></p>
    <p>
      <input v-model="latent" type="range" :min=minLatent :max=maxLatent :step=stepLatent />
    </p>
    
  </div>
</template>

<script>
import ScatterChart from '@/components/scatterChart'
import coords from '@/assets/coords.json'
export default {
  name: 'Visualize1D',
  components: {
    ScatterChart
  },
  data() {
    return {
      coords: coords,
      torque: "0.100",
      latent: "0.00",
      minTorque: "0.010",
      maxTorque: '0.180',
      stepTorque: '0.010',
      minLatent: "-1.00",
      maxLatent: '1.00',
      stepLatent: '0.10',
    }
  },
  methods: {
    coordsData() {
      var torque = Number(this.torque).toFixed(3)
      var latent = Number(this.latent).toFixed(2)
      return this.coords[torque][latent]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
