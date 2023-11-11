<script setup lang="ts">

import ValidateTextField from '@/components/field/validate/validate-text-field.vue'
import { ref } from 'vue'
import TextField from '@/components/field/text-field.vue'
const test = ref()
</script>

<template>
  <div class="form">
    {{test}}
    <text-field v-model="test" label="Тестовый заголовок"></text-field>
  </div>
</template>
