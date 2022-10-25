<template>
  <div id="app">
    <MyHeader />
    <main>
      <div class="content">
        <Visualize/>
      </div>
    </main>
    <MyFooter />
  </div>
</template>

<script>
// import Visualize from './components/Visualize1D.vue'
import Visualize from './components/Visualize2D.vue'
import MyHeader from './components/MyHeader.vue'
import MyFooter from './components/MyFooter.vue'

export default {
  name: 'App',
  components: {
    Visualize,
    MyHeader,
    MyFooter
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.content {
  max-width: 1230px;
  padding: 60px 15px;
  margin-left: auto;
  margin-right: auto;
}
</style>
