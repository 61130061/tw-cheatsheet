<script lang="ts">
  const getColor = (name) => {
    let className = ['py-2']
    if (name.toLowerCase() === 'class') className.push('text-blue-500')
    else if (name.toLowerCase() === 'properties') className.push('text-purple-500')
    else className.push('text-gray-500')

    if (name.toLowerCase() !== 'class') className.push('break-words')

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
    <div v-if="showInfo" class="bg-gray-100 rounded-lg px-3 m-2">
      <table class="table-auto text-left w-full">
        <thead class="border-b-2">
          <tr>
            <th v-for="(v, k) in data.table[0]" class="py-3">{{k}}</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(c) in data.table">
            <td v-for="(v, k) in c" v-bind:class="getColor(k)">{{v}}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>