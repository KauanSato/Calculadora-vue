<script setup>
defineProps({ modelValue: String })
const emit = defineEmits(['update:modelValue'])
</script>

<template>
    <div>
        <select class="seletor text-center mt-3 mb-3 rounded p-2" :value="modelValue"
            @change="event => emit('update:modelValue', event.target.value)">
            <option value="+">Adição (+)</option>
            <option value="-">Subtração (-)</option>
            <option value="X">Multiplicação (X)</option>
            <option value="÷">Divisão (÷)</option>
        </select>
    </div>
</template>

<style scoped>
.seletor{
    border-radius: 15px;
    padding: 1px;
    font-size: 15px;
}
</style>
