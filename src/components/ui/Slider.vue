<template>
  <div class="flex items-center w-full">
    <div class="relative flex-1 flex items-center">
      <input
        type="range"
        :min="min"
        :max="max"
        :step="step"
        v-model="internalValue"
        class="slider-thumb"
        @input="updateValue"
      />
      <div class="slider-track"></div>
      <div class="slider-circle" :style="circleStyle"></div>
      <div class="slider-progress" :style="progressStyle"></div>
    </div>
    <span class="ml-4 text-3xl font-medium">{{ internalValue }}%</span>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, watch } from 'vue'

const props = defineProps({
  modelValue: { type: Number, default: 10 },
  min: { type: Number, default: 0 },
  max: { type: Number, default: 100 },
  step: { type: Number, default: 1 },
})
const emit = defineEmits(['update:modelValue'])

const internalValue = ref(props.modelValue)
watch(
  () => props.modelValue,
  (v) => (internalValue.value = v),
)

function updateValue(e: Event) {
  const val = Number((e.target as HTMLInputElement).value)
  internalValue.value = val
  emit('update:modelValue', val)
}

const circleStyle = computed(() => {
  const percent = ((internalValue.value - props.min) / (props.max - props.min)) * 100
  return {
    left: `calc(${percent}% - 24px)`,
    background: '#D8FF4F',
  }
})

const progressStyle = computed(() => {
  const percent = ((internalValue.value - props.min) / (props.max - props.min)) * 100
  return {
    width: percent + '%',
    background: '#D8FF4F',
  }
})
</script>

<style scoped>
.slider-track {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  height: 6px;
  background: #e7ebdf;
  border-radius: 3px;
  transform: translateY(-50%);
  z-index: 0;
}
input[type='range'].slider-thumb {
  position: relative;
  width: 100%;
  height: 40px;
  background: transparent;
  appearance: none;
  z-index: 2;
}
input[type='range'].slider-thumb::-webkit-slider-thumb {
  appearance: none;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background: none;
  cursor: pointer;
  z-index: 3;
}
input[type='range'].slider-thumb::-moz-range-thumb {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background: none;
  cursor: pointer;
  z-index: 3;
}
input[type='range'].slider-thumb::-ms-thumb {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background: none;
  cursor: pointer;
  z-index: 3;
}
.slider-circle {
  position: absolute;
  top: 50%;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background: #d8ff4f;
  transform: translateY(-50%);
  z-index: 1;
  pointer-events: none;
}
.slider-progress {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  height: 6px;
  background: #D8FF4F;
  border-radius: 3px;
  transform: translateY(-50%);
  z-index: 1;
  pointer-events: none;
}
</style>
