<template>
  <input v-model="inputValue" @input="onInput" />
</template>

<script setup>
import { ref, watch } from 'vue'

const props = defineProps({
  modelValue: String,
  debounce: {
    type: Number,
    default: 300
  }
})
const emit = defineEmits(['update:modelValue'])

const inputValue = ref(props.modelValue)
watch(() => props.modelValue, (val) => {
  inputValue.value = val
})

let timeout
const onInput = () => {
  clearTimeout(timeout)
  timeout = setTimeout(() => {
    emit('update:modelValue', inputValue.value)
  }, props.debounce)
}
</script>
