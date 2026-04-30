<template>
  <div class="my-4 font-geist border-b-2 border-neutral-content">
    <label for="input" class="text-accent font-medium">{{ label }}</label>
    <div class="flex items-center">
      <span v-if="leading" class="mr-2 mt-2 text-4xl font-medium text-primary">
        {{ leading }}
      </span>
      <input
        id="input"
        type="text"
        class="text-4xl font-medium text-primary pb-4 pt-6 w-full focus:outline-0 placeholder:text-neutral-content bg-transparent "
        :class="fontClasses"
        :placeholder="placeholder"
        :value="modelValue"
        @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  modelValue: {
    type: String,
    default: '',
  },
  label: {
    type: String,
    default: '',
  },
  placeholder: {
    type: String,
    default: '',
  },
  font: {
    type: String,
    default: 'Geist',
  },
  leading: {
    type: String,
    default: '',
  },
})

const fontClasses = computed(() => ({
  [`font-${props.font.toLowerCase()}`]: true,
}))
</script>

<style scoped></style>
