<template>
  <CustomInput
    label='Name'
    v-model="name"
    type='text'
   /> <br><br>
   <CustomInput
    label='Last name'
    v-model="lastName"
    type='text'
   /> <br><br>
   <CustomInput
    label='Hobbies'
    v-model="hobbies.music"
    type='text'
   /> <br><br>
  <CustomSelect
    :options='newArray'
    label='Custom Select'
    v-model="opt"
  /> <br> <br>
  <CustomCheckbox 
    label="First Option"
    v-model="first"
  /> <br>
   <CustomCheckbox 
    label="Second Option"
    v-model="second"
  />
</template>

<script>

import {reactive, ref, toRefs } from 'vue';

import CustomInput from './components/CustomInput.vue'
import CustomSelect from './components/CustomSelect.vue'
import CustomCheckbox from './components/CustomCheckbox.vue'

export default {
  name: 'App',
  components: {
    CustomInput,
    CustomSelect,
    CustomCheckbox,
  },
  setup() {
    const opt = ref();
    const variables = reactive({
      name: '',
      lastName: '', 
      age: null,
      hobbies: {
        music: '',
        sports: '',
        arts: '',
        read: '',
      },
    });

    const booleans = reactive({
      first: false,
      second: true,
    });

     const newArray = [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ];

    return { ...toRefs(variables), ...toRefs(booleans), newArray, opt, }
  }
}



</script>

<style>
  .input {
    margin-left: 20px;
  }

</style>
