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
import {BsModal} from "../../../../dist";
export default defineComponent({
  name: 'HelloWorld',
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
    BsModal
  }
});
</script>