<script setup>
defineProps(['value']);
defineEmits(['update:modelValue']);
</script>

<template>
    <label class="block font-medium text-sm text-gray-700">
        <span v-if="value">{{ value }}</span>
        <span v-else><slot /></span>
        <input @input="$emit('update:modelValue',$event.target.value)">
    </label>
</template>
