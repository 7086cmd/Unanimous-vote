<script setup lang="ts">
import { position, candidates, candidateSex, presents } from './config'
import { ref } from 'vue'

const candidate = ref(candidates)

if (candidate.value.length === 2) {
  candidate.value = `${candidate.value[0]}　${candidate.value[1]}`
}

if (candidateSex === 'F') {
  candidate.value = `${candidate.value}（女）`
}
</script>

<template>
  <div class="flex flex-col items-center min-h-screen bg-blue-800">
    <h1 class="text-6xl font-bold pt-16 text-white mb-4">{{ position }}</h1>
    <div class="text-white text-6xl font-bold">
      <p>候选人　{{ candidate }}</p>
    </div>
    <div>
      <table class="w-full text-white text-4xl font-bold">
        <tbody>
          <tr class="py-1">
            <td class="px-8 text-4xl">赞　成</td>
            <td class="mx-4 px-8 text-4xl text-right">{{ presents }} 票</td>
          </tr>
          <tr class="py-1">
            <td class="px-8 text-4xl">反　对</td>
            <td class="mx-4 px-8 text-4xl text-right">0 票</td>
          </tr>
          <tr class="py-1">
            <td class="px-8 text-4xl">弃　权</td>
            <td class="mx-4 px-8 text-4xl text-right">0 票</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style>
body {
  font-family: 'Times New Roman', '宋体';
  background-color: black;
  overflow: hidden !important;
}
</style>
