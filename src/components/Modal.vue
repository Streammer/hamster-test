<template>
    <div class="modal" @click="handleClick">
        <div class="modal__content" @click.stop>

        </div>
    </div>
</template>
<script setup>
import { defineEmits } from 'vue'; 
const emit = defineEmits(['close']); 
const handleClick = () => { 
    emit('close', false); 
};
</script>
<style scoped>
.modal {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.90);
    z-index: 2;
    cursor: pointer;
    display: flex;
}

.modal__content {
    width: 318px;
    min-height: 295px;
    margin: auto;
    border: 1px solid red;
}
</style>