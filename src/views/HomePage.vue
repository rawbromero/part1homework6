<script setup>
import { onMounted, ref } from 'vue'
import BaseTitle from '@/components/BaseTitle.vue';
import useAPI from '@/composables/useAPI'

const { categories, getGategories } = useAPI()

onMounted(async () => {
  await getGategories()
  
})
  

</script>

<template>
  <BaseTitle>TRIVIA APPLICATION</BaseTitle>
  <div v-for="category in categories" :key="category.id">
    {{ category.name }}

    
  </div>

</template>

