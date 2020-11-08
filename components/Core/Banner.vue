<template v-slot:activator="{ on, attrs }">
  <div id="inspire">
    <v-parallax src="/" class="main-gradient" height="450" jumbotron>
      <v-container>
        <v-row>
          <v-col md="6" xl="5">
            <h1
              class="motto text-center white--text"
              style="
                font-size: 48px !important;
                line-height: 68px !important;
              "
            >
              Software Engineer
            </h1>
            <p class="text-center mt-5" style="font-size: 20px">
              Gemmechu Mohammed
            </p>
          </v-col>
          <v-col
            md="8"
            xl="6"
            class="pr-xl-12"
            style="bottom: 0; position: absolute; right: 0; padding-bottom: 0"
          >
            <v-img src="/gemme.png" style="min-height: 10rem" />
          </v-col>
        </v-row>
      </v-container>
    </v-parallax>
  </div>
</template>
<script>
export default {
  mounted() {
    this.$store.dispatch("setActiveLink", "colored");
  }
};
</script>
