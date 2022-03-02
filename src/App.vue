<template>
  <CustomInput
    label='Name'
    v-model="name"
    type='text'
   /> <br>
   <CustomInput
    label='Last name'
    v-model="lastName"
    type='text'
   /> <br>
   <CustomInput
    label='Hobbies'
    v-model="hobbies.music"
    type='text'
   />

   <p>{{name}}</p>
   <p>{{lastName}}</p>
   <p>{{hobbies.music}}</p>

  <CustomSelect
    :options='newArray'
    label='Custom Select'
    v-model="opt"
  />

  {{opt}}

</template>

<script>

import {reactive, ref, toRefs } from 'vue';

import CustomInput from './components/CustomInput.vue'
import CustomSelect from './components/CustomSelect.vue'

export default {
  name: 'App',
  components: {
    CustomInput,
    CustomSelect,
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
      }
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

    return { ...toRefs(variables), newArray, opt }
  }
}



</script>

<style>
  .input {
    margin-left: 20px;
  }

</style>
