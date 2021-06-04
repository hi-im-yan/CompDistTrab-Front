<template>
  <v-footer
      color="deep-purple"
      padless
  >
    <v-row
        justify="center"
        no-gutters
    >
      <v-btn
          @click="goToFrontRepoGitHub"
          color="white"
          text
          rounded
          class="my-2"
      >
        Repositório Front
      </v-btn>
      <v-btn
          @click="goToFrontRepoGitHub"
          color="white"
          text
          rounded
          class="my-2"
      >
        Repositório Back
      </v-btn>

    </v-row>
  </v-footer>
</template>

<script>
export default {
  name: "Footer",

  data: () => ({
    link_front_repo: "https://github.com/hi-im-yan/CompDistTrab-Front",
  }),

  methods:{
    goToFrontRepoGitHub: function () {
      window.open(this.link_front_repo, "_blank");
    }
  }
}
</script>

<style scoped>

</style>