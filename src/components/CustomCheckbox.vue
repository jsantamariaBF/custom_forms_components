<template>
    <label v-if="label">{{ label }}</label>
    <input 
        type="checkbox"
        :checked="modelValue"
        @change="$emit('update:modelValue', $event.target.checked)"
    >
</template>

<script>
export default {
    name: 'CustomCheckbox',
    props: {
        label: {
            type: String,
            default: ''
        },
        modelValue: {
            type: Boolean,
            default: false,
        }
    }
}
</script>

<style>

</style>