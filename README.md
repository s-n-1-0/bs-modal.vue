# bs-modal.vue
Use bootstrap modal with vue3.
Supports the use of multiple modals.

## Preparing
Create a vue3 project and install bootstrap5.

(Methods omitted)

## Installation
```
npm install bs-modal-vue
```

## How to Use
`sample.vue`
```vue
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
import {bsModal} from "bs-modal-vue";
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
    bsModal
  }
});
</script>
```
