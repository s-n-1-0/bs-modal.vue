<template>
  <HelloWorld/>
  <hr>
  readme.md ↓
  <Readme/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HelloWorld from './components/HelloWorld.vue';
import Readme from './components/Readme.vue';

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld,
    Readme
}
});
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
</style>
