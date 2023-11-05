<script setup>
const props = defineProps(['data', 'url'])
console.log(props)
function select(url) {
  window.location.href = window.location.href+"cardpage/"+url;
}
</script>
<template>
  <div class="shadow rounded-4 p-5" v-on:click="select(url)">
    
    <h1>{{data.name}}</h1>
    <p>{{data.email}}</p>
    <p>{{url}}</p>

    <!-- <img src="/icon.png" alt="icon"/> -->
  </div>
</template>