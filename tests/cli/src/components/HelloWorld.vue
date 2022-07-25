<template>
  <div class="hello">
    <h1>Modal Samples</h1>
    <bs-modal ref="bodyOnlyModalRef">
      <h1>Body</h1>
    </bs-modal>
    <bs-modal ref="footerModalRef">
        <h1>Body</h1>
      <template v-slot:footer>
        <h1>Footer</h1>
      </template>
    </bs-modal>
    <modal-in-modal ref="modalInModalRef">
      <button type="button" class="btn btn-primary m-1" v-on:click="showModal(modalInModalRef)">Show Modal in Modal</button>
    </modal-in-modal>
    <button type="button" class="btn btn-primary m-1" v-on:click="showModal(bodyOnlyModalRef)">Show Body Only Modal</button><br>
    <button type="button" class="btn btn-primary m-1" v-on:click="showModal(footerModalRef)">Show Modal</button><br>
    <button type="button" class="btn btn-primary m-1" v-on:click="showModal(modalInModalRef)">Show Modal in Modal</button><br>
    <hr>
    <h3>.modal Settings</h3>
    <bs-modal ref="staticBackdropRef" data-bs-backdrop="static">
      <h1> Static Backdrop</h1>
    </bs-modal>
    <button type="button" class="btn btn-primary m-1" v-on:click="showModal(staticBackdropRef)">Static Backdrop</button>
    <hr>
    <h3>.modal-dialog Settings</h3>
    <bs-modal ref="scrollingLongContentRef" :modal-dialog-settings="['modal-dialog-scrollable']">
      Scrolling Long Content
      ...<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
      end
    </bs-modal>
    <bs-modal ref="xlSizeModalRef" :modal-dialog-settings="['modal-xl']"><h1>XL Size!</h1></bs-modal>
    <bs-modal ref="fullscreenModalRef" :modal-dialog-settings="['modal-fullscreen']"><h1>Fullscreen!</h1></bs-modal>
    <button type="button" class="btn btn-primary m-1" v-on:click="showModal(scrollingLongContentRef)">Scrolling Long Content</button>
    <button type="button" class="btn btn-primary m-1" v-on:click="showModal(xlSizeModalRef)">Xl Size</button>
    <button type="button" class="btn btn-primary m-1" v-on:click="showModal(fullscreenModalRef)">Fullscreen</button>
  </div>
</template>

<script lang="ts">
import { defineComponent,ref } from 'vue';
import {BsModal,BsModalInterface} from "../../../../dist";
import ModalInModal from "./ModalInModal.vue";
export default defineComponent({
  name: 'HelloWorld',
  setup(){
    // eslint-disable-next-line @typescript-eslint/no-explicit-any
    const makeRef  = () => ref<any>(null);
    return{
      bodyOnlyModalRef:makeRef(),
      footerModalRef:makeRef(),
      modalInModalRef:makeRef(),
      staticBackdropRef:makeRef(),
      scrollingLongContentRef:makeRef(),
      xlSizeModalRef:makeRef(),
      fullscreenModalRef:makeRef(),
      showModal(refValue:BsModalInterface){
        refValue?.showModal();
      }
    }
  },
  components:{
    BsModal,
    ModalInModal
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
