<template>
  <div v-if="job">
    <h1>{{ job.title }}</h1>
    <p>the job id is {{props.id}}</p>
    <p>{{job.details}}</p>
  </div>
  <div v-else>
    <p>Loading job details...</p>
  </div>

</template>

<script setup>
import { useRouter, useRoute } from 'vue-router'
import {onMounted, ref} from "vue";
const name='JobDetails'
const router = useRouter()
const props = defineProps(['id'])
const route = useRoute()
const jobId = route.params.id
let job = ref(null)


onMounted(()=>{
  fetch('http://localhost:3000/jobs/' + props.id)
      .then(res=>res.json())
      .then(data=>{
        job.value = data
      })
      .catch(err=>console.log(err.message))
})
</script>

<style scoped>

</style>
