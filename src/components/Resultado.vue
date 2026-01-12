<script setup>
    defineProps({ resultado: [String] })
</script>

<template>
    <p class="resultado text-center"><strong>{{ resultado }}</strong></p>
</template>

<style scoped>
.resultado {
    font-size: 25px;
}
</style>
