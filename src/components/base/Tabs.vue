<script lang="ts" setup>
import { provide, ref, watchEffect } from 'vue';

interface Props {
  tabs: string[]
  modelValue: number
}

interface Emit {
  (e: 'update:modelValue', value: number): void
}

const props = defineProps<Props>()
const emit = defineEmits<Emit>()
const selectedTab = ref(props.modelValue)

provide('selectedTab', selectedTab)

const handleTabSelect = (index: number) => {
  selectedTab.value = index
  emit('update:modelValue', index)
}

</script>
<template>
  <div class="tabs">
    <div class="tabs__header flex">
      <div v-for="(tab, index) in tabs" :key="index"
        :class="modelValue === index ? 'boder-blue-5': 'border-transparent'"
        class="flex-1 text-center py-2 border-b-2 cursor-pointer" @click="handleTabSelect(index)">
        {{ tab }}
      </div>
    </div>
    <div class="tabs__body p-4">
      <slot />
    </div>
  </div>
</template>