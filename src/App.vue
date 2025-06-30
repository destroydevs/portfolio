<template>
  <the-header></the-header>
  <user-card></user-card>
  <news></news>
</template>

<script>
import HeaderComponentVue from './components/HeaderComponent.vue'
import NewsComponentVue from './components/NewsComponent.vue'
import UserCardComponentVue from './components/UserCardComponent.vue'
export default {
  components: {
    "the-header": HeaderComponentVue,
    "user-card": UserCardComponentVue,
    "news": NewsComponentVue
  }
}
</script>

<style scoped>

p {
    margin-top: 1000px;
}

</style>