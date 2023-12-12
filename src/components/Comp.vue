<script setup lang="ts">
import { InputNumberProps, InputProps } from 'ant-design-vue'
import { PropType } from 'vue'

defineOptions({
  name: 'Comp',
})

defineProps({
  inputProps: {
    type: Object as PropType<InputProps>,
    default: () => ({}),
  },
  numberProps: {
    type: Object as PropType<InputNumberProps>,
    default: () => ({}),
  },
  inputSlots: {
    type: Object,
    default: () => ({}),
  },
  numberSlots: {
    type: Object,
    default: () => ({}),
  },
})
</script>

<template>
  <div>
    <a-input v-bind="{ ...inputProps }">
      <template v-for="(_, name) in inputSlots" :key="name" #[name]>
        <slot :name="inputSlots[name]" />
      </template>
    </a-input>
    <a-input-number v-bind="{ ...numberProps }">
      <template v-for="(_, name) in numberSlots" :key="name" #[name]>
        <slot :name="numberSlots[name]" />
      </template>
    </a-input-number>
  </div>
</template>

<style scoped></style>
