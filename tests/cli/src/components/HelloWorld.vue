<template>
  <div class="hello">
    <h1>Modal Samples</h1>
    <bs-modal ref="bodyOnlyModalRef">
      <h1>Body</h1>
    </bs-modal>
    <button type="button" class="btn btn-primary" v-on:click="showModal()">Show Modal</button>
  </div>
</template>

<script lang="ts">
import { defineComponent,ref } from 'vue';
import {bsModal} from "../../../../dist";
export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  setup(){
    // eslint-disable-next-line @typescript-eslint/no-explicit-any
    const bodyOnlyModalRef = ref<any>(null);
    return{
      bodyOnlyModalRef,
      showModal(){
        bodyOnlyModalRef.value?.showModal();
      }
    }
  },
  components:{
    bsModal
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
