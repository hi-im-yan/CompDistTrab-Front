<template>
  <v-app>
    <v-main>
      <router-view/>
    </v-main>
    <Footer></Footer>
  </v-app>
</template>

<script>
import Footer from './components/Footer/Footer'
export default {
  components: {
    Footer
  }
}
</script>
<style lang="scss">

</style>
