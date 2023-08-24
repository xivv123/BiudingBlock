<template>
    <input :value="modelValue" @input="updateValue" :placeholder="placeholder" />
  </template>
  
  <script lang="ts">
  import { defineComponent, PropType } from 'vue';
  
  export default defineComponent({
    name: 'B-Input',
    props: {
      modelValue: {
        type: String as PropType<string>,
        default: ''
      },
      placeholder: {
        type: String as PropType<string>,
        default: ''
      }
    },
    emits: ['update:modelValue'],
    setup(props, { emit }) {
      const updateValue = (event: Event) => {
        emit('update:modelValue', (event.target as HTMLInputElement).value);
      };
  
      return {
        updateValue
      };
    }
  });
  </script>