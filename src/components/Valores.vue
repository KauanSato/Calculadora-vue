<script setup>
    defineProps({modelValue: Number, placeholder: String})

    const emit = defineEmits(['update:modelValue'])

    function updateValue(event) {
        emit('update:modelValue', Number(event.target.value))
    }
</script>

<template>
<div class="input">
    <input class="space text-center p-1" type="number" @input="updateValue" :value="modelValue" :placeholder="placeholder">
</div>
</template>

<style scoped>
.input {
    display: block;
    padding: 10px;
}

.space {
    border-radius: 15px;
    width: 100%;
    padding: 10px;
    font-size: 20px;
}
</style>