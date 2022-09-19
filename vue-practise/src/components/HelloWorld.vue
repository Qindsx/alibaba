<script setup lang="ts">
import { onMounted, ref } from 'vue'

const randomNumber = ref((Math.random() * 100).toFixed(2))

onMounted(()=>{
  const Timer =  setInterval(()=>{
    console.log(123);
    randomNumber.value = (Math.random() * 100).toFixed(2)
  },2000)
})

defineProps<{ msg: string }>()

const count = ref(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
  </div>

  <div class="random">
    <h1>{{ randomNumber }}%</h1>
  </div>

</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
