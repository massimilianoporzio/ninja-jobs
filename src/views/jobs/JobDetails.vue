<template>
  <h1>Job Details Page</h1>
  <p>the job id is {{props.id}}</p>
</template>

<script setup>
import { useRouter, useRoute } from 'vue-router'
const name='JobDetails'
const router = useRouter()
const props = defineProps(['id'])
const route = useRoute()
const jobId = route.params.id
</script>

<style scoped>

</style>