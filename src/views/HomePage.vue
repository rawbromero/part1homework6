<script setup>
import { onMounted, ref } from 'vue'
import BaseTitle from '@/components/BaseTitle.vue';
import useAPI from '@/composables/useAPI';
import { RouterLink } from 'vue-router';

const { categories, getCategories } = useAPI()

onMounted(async () => {
  await getCategories()
})
</script>

<template>
  <BaseTitle>TRIVIA APPLICATION</BaseTitle>
  <div class="grid flex-grow grid-cols-4 gap-12 m-20">
    <RouterLink v-for="category in categories" 
    :key="category.id"
    :to="`/question/category/${category.id}`"
    class="bg-white-600 text-blue-500 text-center flex h-32 items-center justify-center rounded-lg border-4 border-red-500 py-3 font-bold uppercase hover:cursor-pointer hover:border-blue-600 hover:bg-purple-700-400 hover:text-orange-300 transition-colors duration-350">
      {{ category.name }}
    </RouterLink>
  </div>
  
</template>