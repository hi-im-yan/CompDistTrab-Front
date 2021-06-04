<template>
<v-row>
  <v-card
      class="mx-auto my-12"
      max-width="374"
  >

    <v-img
        height="350"
        src="yan.png"
    ></v-img>

    <v-card-title>Yan Sérgio Yudi Ajiki</v-card-title>

    <v-card-text>
      <v-row
          align="center"
          class="mx-0"
      >
      </v-row>

      <div class="my-4 text-subtitle-1">
        Engenharia de Software
      </div>

      <div>Práticas de Web Dev utilizando Django e Vue. Linguagem preferida: Python. <p> Comeu o cu de quem ta lendo</p></div>
    </v-card-text>

    <v-divider class="mx-4"></v-divider>

    <v-card-title>Participações no trabalho</v-card-title>

    <v-card-text>

        <v-chip color="cyan darken-2" dark>Frontend</v-chip>
    </v-card-text>
    <v-card-actions>
      <v-btn
          color="deep-purple lighten-2"
          outlined
          @click="yanGithub()"
      >
        Github
      </v-btn>
      <v-btn
          color="deep-purple lighten-2"
          outlined
          @click="yanLinkedin()"
      >
        Linkedin
      </v-btn>
    </v-card-actions>

  </v-card>
  <v-card
      class="mx-auto my-12"
      max-width="374"
  >


    <v-img
        height="350"
        src="vinicius_temp.jpeg"
    ></v-img>

    <v-card-title>Vinicius Orejana Valente</v-card-title>

    <v-card-text>
      <v-row
          align="center"
          class="mx-0"
      >
      </v-row>

      <div class="my-4 text-subtitle-1">
        Engenharia de Software
      </div>

      <div>Dev Frontend utilizando Typescript, Angular e Vue. Linguagem preferida: Javascript<p>Ele é</p></div>
    </v-card-text>

    <v-divider class="mx-4"></v-divider>

    <v-card-title>Participações no trabalho</v-card-title>
    <v-card-text>
        <v-chip color="cyan darken-2" dark>Frontend</v-chip>
    </v-card-text>

    <v-card-actions>
      <v-btn
          color="deep-purple lighten-2"
          outlined
      >
        Github
      </v-btn>
      <v-btn
          color="deep-purple lighten-2"
          outlined
      >
        Linkedin
      </v-btn>
    </v-card-actions>
  </v-card>
  <v-card
      class="mx-auto my-12"
      max-width="374"
  >
    <v-img
        height="350"
        src="gustavo.pn.jpeg"
    ></v-img>

    <v-card-title>Gustavo Marães Ferreira</v-card-title>

    <v-card-text>
      <v-row
          align="center"
          class="mx-0"
      >
      </v-row>

      <div class="my-4 text-subtitle-1">
        Sistemas de Informação
      </div>

      <div>Dev Backend utilizando SpringBoot e Postgres. Linguagem preferida: Java<p>Camunda developer</p></div>
    </v-card-text>

    <v-divider class="mx-4"></v-divider>

    <v-card-title>Participações no trabalho</v-card-title>

    <v-card-text>
      <v-chip color="green darken-2" dark>Backend</v-chip>
    </v-card-text>

    <v-card-actions>
      <v-btn
          color="deep-purple lighten-2"
          outlined
      >
        Github
      </v-btn>
      <v-btn
          color="deep-purple lighten-2"
          outlined
      >
        Linkedin
      </v-btn>
    </v-card-actions>
  </v-card>

</v-row>
</template>

<script>
export default {
  name: "Integrantes",

  data: () => ({

  }),

  methods: {
    yanGithub(){
      window.open("https://github.com/hi-im-yan/", "_blank");
    },
    yanLinkedin(){
      window.open("https://www.linkedin.com/in/yan-ajiki-59ba74190/", "_blank");
    }
  }
}
</script>

<style scoped>

</style>