<template>
    <label v-if="label">{{ label }}</label>
    <input 
        v-bind="$attrs"
        :placerholder='label'  
        :value='modelValue' 
        @input="$emit('update:modelValue', $event.target.value)"
        class="input"
    />
</template>

<script>
    export default {
        emits: ['update:modelValue'],
        props: {
            label: {
                type: String,
                default: '',
            },
            modelValue: {
                type: [Number, String],
                default: '',
            },
        },
    };
</script>

<style scoped>

</style>
