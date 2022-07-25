<template>
    <bs-modal ref="thisRef">
        <button type="button" class="btn btn-primary mb-1" v-on:click="showModalInModal(modalInModalRef)">Show Modal in Modal</button>
    </bs-modal>
    <bs-modal ref="modalInModalRef">
        <h1> Modal in Modal</h1>
    </bs-modal>
</template>
<script lang="ts">
import { defineComponent,ref } from 'vue';
import {BsModal,BsModalInterface} from "../../../../dist";
export default defineComponent({
    setup(){
        // eslint-disable-next-line @typescript-eslint/no-explicit-any
        const makeRef  = () => ref<any>(null);
        const thisRef = makeRef();
        return {
            modalInModalRef:makeRef(),
            thisRef,
            showModal(){
                thisRef.value?.showModal();
            },
            showModalInModal(refValue:BsModalInterface){
                refValue?.showModal();
            }
        }
    },
    components:{
        // eslint-disable-next-line vue/no-unused-components
        BsModal
    }
});
</script>