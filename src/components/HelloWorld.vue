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
  name: 'HelloWorld',
  components: {
    ScatterChart
  },
  data() {
    return {
      coords: coords,
      torque: "0.10",
      latent: "0.00",
      minTorque: "0.01",
      maxTorque: '0.18',
      stepTorque: '0.01',
      minLatent: "-2.4",
      maxLatent: '2.4',
      stepLatent: '0.2',
    }
  },
  methods: {
    coordsData() {
      var x = Number(this.torque).toFixed(2)
      var y = Number(this.latent).toFixed(2)
      // if (y == '0.00') {
      //   y  = '-0.00'
      // }
      return this.coords[x][y]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
