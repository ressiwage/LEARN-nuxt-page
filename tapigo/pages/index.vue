<script setup>
import { ref } from 'vue'
import CardVue from '../components/Card.vue'

const posts = ref([])
fetch('http://127.0.0.1:4000', {
headers: {
  'Accept': 'application/json'
}})
.then(response => response.json())
.then(json => {posts.value=json })

</script>

<template>
  <div class="container">
    <div class="row">
        <div v-for="(card, index) in posts" :key="card.name" class="col-3 h-50">
            <CardVue :data="card" :url="index"></CardVue>
        </div>
    </div>

  </div>
</template>

<script>
// import axios from 'axios'

export default {
  
  name: 'IndexPage',
}
</script>
