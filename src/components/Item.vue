<script lang="ts">
  const getColor = (name) => {
    let className = ['py-2']
    if (name === 'class') className.push('text-blue-500')
    else if (name === 'property') className.push('text-purple-500')
    else className.push('text-gray-500')
    return className.join(' ');
  }

  export default {
    props: {
      data: Object
    },
    data() {
      return {
        showInfo: false
      }
    },
    methods: {
      onToggle() {
        this.showInfo = !this.showInfo
      },
      getColor
    }
  }
</script>

<template>
  <div class="mb-3">
    <div @click="onToggle" class="p-3 bg-white rounded drop-shadow font-[600] hover:cursor-pointer">{{data.name}}</div>
    <div v-if="showInfo" class="bg-gray-100 rounded-lg px-3 m-2 my-3">
      <table class="table-auto text-left w-full">
        <thead class="border-b-2">
          <tr>
            <th v-for="(v, k) in data.classes[0]" class="py-3">{{k[0].toUpperCase() + k.substring(1)}}</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(c) in data.classes">
            <td v-for="(v, k) in c" v-bind:class="getColor(k)">{{v}}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>