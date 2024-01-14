<script setup lang="ts">
interface ListItem {
  id: string
  text: string
}

defineProps<{
  item: ListItem
  removeItem: (id: string) => void
}>()
</script>

<template>
  <li class="w-full flex items-center justify-between p-4 border-b border-zinc-800">
    <p>
      {{ item.text }}
    </p>
    <button
      type="button"
      @click="removeItem(item.id)"
      class="bg-amber-800 px-2 rounded-md py-1 hover:bg-amber-600"
    >
      Done
    </button>
  </li>
</template>
