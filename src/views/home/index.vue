<script setup lang="ts">
import Comp from '@/components/Comp.vue'
import { EditOutlined, FormOutlined } from '@ant-design/icons-vue'
defineOptions({
  name: 'MyHome',
})

const inputSlots = {
  prefix: 'input-prefix',
}
const numberSlots = {
  prefix: 'number-prefix',
}
</script>

<template>
  <div class="p-5">
    <a-button type="primary" class="rounded">按钮</a-button>
    <ADivider />
    <Comp :input-slots="inputSlots" :number-slots="numberSlots">
      <template #input-prefix>
        <EditOutlined />
      </template>
      <template #number-prefix>
        <FormOutlined />
      </template>
    </Comp>
  </div>
</template>

<style lang="scss" scoped></style>
