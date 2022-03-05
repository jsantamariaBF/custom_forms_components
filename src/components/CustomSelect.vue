<template>
    <label for="" v-if="label">{{label}}</label>
    <select 
        v-bind="{...$attrs, 
            onChange: ($event) => { $emit('update:modelValue', $event.target.value) }}"
        :value='modelValue'
    >
        <option 
            v-for="(option, index) in options" 
            :key="index"
            :selected="option === modelValue"
        >
            {{option}}
        </option>
    </select>
</template>

<script>
    export default {
        props: {
            label: {
                type: String,
                default: '',
            },
            options: {
                type: Array,
                required: true,
            },
            modelValue: {
                type: [String, Number],
                default: ''
            },
        },
        emits: ['update:modelValue'],
    };
</script>

<style>

</style>