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
    <bs-modal ref="bodyOnlyModalRef" class="fade">
      <h1>Body</h1>
    </bs-modal>
    <button type="button" class="btn btn-primary" v-on:click="showModal()">Show Modal</button>
  </div>
</template>
<script lang="ts">
import { defineComponent,ref } from 'vue';
import {BsModal} from "bs-modal-vue";
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
```
### Options
+ Bootstrap5 docs
  + https://getbootstrap.jp/docs/5.0/components/modal/

#### Use Footer
```vue
<bs-modal>
    <h1>Body</h1>
  <template v-slot:footer>
    <h1>Footer</h1>
  </template>
</bs-modal>
```
#### Fade Animation
```
<bs-modal class="fade">
    <h1>Body</h1>
</bs-modal>
```
#### .modal Settings
```vue
<bs-modal data-bs-backdrop="static">
  <h1> Static Backdrop</h1>
</bs-modal>
```

#### .modal-dialog Settings
```
<bs-modal :modal-dialog-settings="['modal-fullscreen']">
  <h1>Fullscreen!</h1>
</bs-modal>
```

Others can be found here.
  + https://github.com/s-n-1-0/bs-modal.vue/tree/main/tests/cli/src/components

# PR / Issues
Please PR or Issues if you have any questions.