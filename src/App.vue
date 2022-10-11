<script lang="ts">
import Navbar from "./components/Navbar.vue";
import Item from "./components/Item.vue";

import layout from "./data/layout.json";
import flexAndGrid from "./data/FnG.json";
import spacing from "./data/Spacing.json";
import sizing from "./data/Sizing.json";
import typography from "./data/Typography.json";
import backgrounds from "./data/Backgrounds.json";

export default {
  components: {
    Navbar,
    Item
  },
  data() {
    return {
      layout,
      flexAndGrid,
      spacing,
      sizing,
      typography,
      backgrounds
    }
  }
}
</script>

<template>
  <div class="h-screen flex flex-col dark:bg-gray-900 text-gray-800 dark:text-gray-50">
    <Navbar />
    <div class="flex-1">
      <div class="m-5 flex flex-wrap gap-5">
        <div class="bg-gray-200 p-2 rounded-lg w-[350px] h-fit">
          <div class="px-3 py-2 mb-2 font-bold">Layout</div>
          <Item v-for="(data, index) in layout" :data="data" />
        </div>
        <div class="bg-gray-200 p-2 rounded-lg w-[350px] h-fit">
          <div class="px-3 py-2 mb-2 font-bold">Flexbox and Grid</div>
          <Item v-for="(data, index) in flexAndGrid" :data="data" />
        </div>
        <div class="bg-gray-200 p-2 rounded-lg w-[350px] h-fit">
          <div class="px-3 py-2 mb-2 font-bold">Spacing</div>
          <Item v-for="(data, index) in spacing" :data="data" />
        </div>
        <div class="bg-gray-200 p-2 rounded-lg w-[350px] h-fit">
          <div class="px-3 py-2 mb-2 font-bold">Sizing</div>
          <Item v-for="(data, index) in sizing" :data="data" />
        </div>
        <div class="bg-gray-200 p-2 rounded-lg w-[350px] h-fit">
          <div class="px-3 py-2 mb-2 font-bold">Typography</div>
          <Item v-for="(data, index) in typography" :data="data" />
        </div>
        <div class="bg-gray-200 p-2 rounded-lg w-[350px] h-fit">
          <div class="px-3 py-2 mb-2 font-bold">Backgrounds</div>
          <Item v-for="(data, index) in backgrounds" :data="data" />
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
