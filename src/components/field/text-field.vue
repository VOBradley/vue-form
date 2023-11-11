<script setup lang="ts">
import { generateIntUtil } from '@/utils/generate-int.util'
import { ref } from 'vue'
const { label } = defineProps<{
  label: string
}>()
const emit = defineEmits(['update:modelValue'])
const inputId : string = `text-field-${ generateIntUtil(1000) }`
const updateValue = (e: Event) => {
  emit('update:modelValue', (e.target as HTMLInputElement).value)
}

const isFocusField = ref<boolean>(false)
</script>

<template>
  <div class="text-field">
    <div class="text-field__input" :class="{
        'text-field__input-focus' : isFocusField || $attrs.modelValue
    }">
      <label :for="inputId" v-if="label"><span>{{ label }}</span></label>
      <input type="text" :id="inputId" v-model="$attrs.modelValue" @input="updateValue" @focus="isFocusField = true" @blur="isFocusField = false">
    </div>
  </div>
</template>

<style scoped>

</style>