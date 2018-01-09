<template>
  <div>
    <app-header></app-header>
    <app-chooseCard></app-chooseCard>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ChooseCard from './components/ChooseCard'

export default {
  components:  {
    'app-header': Header,
    'app-chooseCard' : ChooseCard,
  },
  data () {
    return {
    }
  }
}
</script>

<style>
  body {
    margin: 0;
  }
</style>
