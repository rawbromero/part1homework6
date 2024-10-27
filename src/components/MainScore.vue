<script setup>
import useScore from '@/composables/UseScore';
    const {score} = useScore()

</script>

<template>

    <span class=""> Main Score: {{ score }}</span>
</template>