<template>
  <div>
    <app-header></app-header>
    <app-chooseCard></app-chooseCard>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header from './components/Header'
import ChooseCard from './components/ChooseCard'
import Footer from './components/Footer'

export default {
  components:  {
    'app-header': Header,
    'app-chooseCard' : ChooseCard,
    'app-footer': Footer,
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
