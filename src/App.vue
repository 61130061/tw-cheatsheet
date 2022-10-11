<script lang="ts">
import Navbar from "./components/Navbar.vue";
import Item from "./components/Item.vue";

import layout from "./data/layout.json";

export default {
  components: {
    Navbar,
    Item
  },
  data() {
    return {
      layout
    }
  }
}
</script>

<template>
  <div class="h-screen flex flex-col dark:bg-gray-900 text-gray-800 dark:text-gray-50">
    <Navbar />
    <div class="flex-1">
      <div class="flex m-5">
        <div class="bg-gray-200 p-2 rounded-lg w-[350px]">
          <div class="px-3 py-2 mb-2 font-bold">Layout</div>
          <Item v-for="(data, index) in layout" :data="data" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
