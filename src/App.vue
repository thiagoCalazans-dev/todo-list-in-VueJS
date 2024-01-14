<script setup lang="ts">
import TaskForm from './components/task-form.vue'
import TodoList from './components/todo-list/todo-list.vue'
import TodoItem from './components/todo-list/list-item.vue'

import { ref } from 'vue'

interface Items {
  id: string
  text: string
}

const items = ref<Items[]>([])

function addItem(text: string): void {
  items.value.push({
    id: Math.random().toString(),
    text: text
  })
}

function removeItem(id: string) {
  const newListItems = items.value.filter((item) => item.id !== id)
  items.value = newListItems
}
</script>
<template>
  <div class="bg-zinc-900 text-zinc-50 min-h-screen flex flex-col">
    <header class="mx-auto container py-16 px-4">
      <h1 class="text-4xl">
        Welcome to another <strong class="font-semibold text-emerald-800">To-do</strong> List
      </h1>
    </header>
    <main class="container mx-auto px-4 space-y-8">
      <TaskForm :addItem="addItem" />
      <TodoList>
        <TodoItem v-for="item in items" :key="item.id" :item="item" :removeItem="removeItem" />
      </TodoList>
    </main>
  </div>
</template>
