<template>
  <Navbar/>
  <div v-if="$store.state.toggle">
    <MainComp/>
  </div>
  <div v-else>
    <About/>
  </div>
</template>

<script setup>
import Navbar from "./components/Navbar.vue";
import MainComp from "./components/MainComp.vue";
import {onMounted} from 'vue'
import {useStore} from "vuex";
import About from "./components/About.vue";

// const weatherData = ref({
//   icon: 'icon',
//   temp: 0,
//   text: 'text',
//   location: 'location',
//   city: 'Seoul',
// })
const store = useStore();

onMounted(() => {
  store.dispatch('getWeather')
})

const onSearchCity = (city) => {
  weatherData.value.city = city;
}
</script>

<style scoped lang="scss">

</style>