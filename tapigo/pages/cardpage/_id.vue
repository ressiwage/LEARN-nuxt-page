<script setup>
import { ref } from 'vue'
import { useRoute } from '@nuxtjs/composition-api'


const route = useRoute()
const post = ref({})
fetch('http://127.0.0.1:4000', {
headers: {
  'Accept': 'application/json'
}})
.then(response => response.json())
.then(json => {post.value=json[route.value.params.id] ; console.log(post.value)})

</script>

<template>
  <div>
    <div class="ms-5">
      <NuxtLink to="/">Home page</NuxtLink>
    </div>

    <div class="container">
      <h1>a user is {{post.name}}</h1>
      <p>email: {{post.email}}</p>
      <p>phone: {{post.phone}}</p>
      <p>address: {{post.address}}</p>
      <p>position name: {{post.position_name}}</p>
      <p>department: {{post.department}}</p>
      <p>hire date: {{post.hire_date}}</p>
    </div>

  </div>
</template>



export default {
  name: 'CardPage',
}