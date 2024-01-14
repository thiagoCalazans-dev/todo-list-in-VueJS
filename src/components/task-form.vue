<script setup lang="ts">
import { ref } from 'vue'

defineProps<{
  addItem: (text: string) => void
}>()

const textInput = ref<string>('')
</script>

<template>
  <form class="space-y-4" @submit.prevent="addItem(textInput)">
    <div id="form-control" class="flex flex-col">
      <label for="task">What you do today?</label>
      <input
        v-model="textInput"
        id="task"
        placeholder="study.. exercise.."
        class="outline-none flex h-9 w-full rounded-md border border-emerald-800 bg-transparent px-3 py-1 text-sm shadow-sm transition-colors file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-zinc-600 focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-emerald-800 disabled:cursor-not-allowed disabled:opacity-50"
      />
    </div>
    <Button
      type="submit"
      class="flex items-center justify-center w-full p-2 text-xl bg-emerald-800 rounded-md hover:bg-emerald-500 transition-transform"
      >Adicionar</Button
    >
  </form>
</template>
