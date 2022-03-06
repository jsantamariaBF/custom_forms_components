<template>
  <label v-if="label">{{ label }}</label>
  <input 
    type="radio" 
    :value="value"
    :checked="modelValue === value"
    @change="$emit('update:modelValue', value)"
    v-bind="$attrs"
  />
</template>

<script>
    export default {
    name: 'CustomCheckbox',
    props: {
        label: {
            type: String,
            default: '',
        },
        modelValue: {
            type: [String, Number],
            default: ''
        },
        value: {
            type: [String, Number],
            required: true,
        },
    }
}
</script>
