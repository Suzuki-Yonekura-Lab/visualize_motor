<template>
  <div id="app">
    <MyHeader />
    <main>
      <div class="content">
        <HelloWorld/>
      </div>
    </main>
    <MyFooter />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MyHeader from './components/MyHeader.vue'
import MyFooter from './components/MyFooter.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
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
