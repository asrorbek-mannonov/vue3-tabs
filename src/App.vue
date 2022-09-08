<script setup lang="ts">
import { ref } from 'vue'
import Tabs from './components/base/Tabs.vue';
import Tab from './components/base/Tab.vue'
const selectedTab = ref<number>(0);
</script>

<template>
  <div>
    <Tabs :tabs="['Galler', 'Contracts', 'About']" v-model="selectedTab">
      <Tab :index="0">
        Gallery tab content
      </Tab>
      <Tab :index="1">
        Contacts tab content
      </Tab>
      <Tab :index="2">
        About tab content
      </Tab>
    </Tabs>
  </div>
</template>
