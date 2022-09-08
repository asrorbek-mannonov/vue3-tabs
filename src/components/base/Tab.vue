<script lang="ts" setup>
import { inject } from 'vue';

defineProps<{
  index: number
}>()

const selectedTab = inject('selectedTab') as number


</script>
<template>
  <div v-show="index === selectedTab">
    <slot />
  </div>
</template>