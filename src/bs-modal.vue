<template>
    <div class="modal fade" tabindex="-1" aria-hidden="true" ref="modal">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <slot name="header"></slot>
                    <button type="button" class="btn-close" aria-label="Close" v-on:click="hideModal()"></button>
                </div>
                <div class="modal-body">
                    <slot></slot>
                </div>
                <div v-if="$slots.footer" class="modal-footer">
                    <slot name="footer"></slot>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import { defineComponent,ref} from 'vue';
import {Modal} from "bootstrap";
export default defineComponent({
    setup(){
        const modalRef = ref(null);
        return {
            modal:modalRef,
            getModalInstance(){
                const myModal = Modal.getInstance(modalRef.value);
                if(myModal) return myModal;
                return new Modal(modalRef.value);
            },
            showModal(){
                const myModal = this.getModalInstance();
                myModal.show();
            },
            hideModal(){
                const myModal = this.getModalInstance();
                myModal.hide();
            }
        }
    }
});
</script>