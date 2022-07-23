<template>
    <div class="modal fade" tabindex="-1" aria-hidden="true" ref="modal">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <slot name="header"></slot>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
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
            showModal(){
                var myModal = new Modal(modalRef.value);
                myModal.show();
            }
        }
    }
});
</script>