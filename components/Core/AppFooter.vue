<template>
  <v-footer padless>
    <v-card flat tile class="white align-center">
      <v-card-text style="width: 100vw">
        <v-container>

          <div class="float-right">
              <p style="font-size: large;" ><b>Contact </b></p>
              <p>gemmechumohammed@gmail.com</p>
              <p>ghassena@umich.edu</p>
              <p>+251938623889</p>
          </div>

        </v-container>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data() {
    return {
      icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"]
    };
  }
};
</script>

<style>
.footer-texts {
  font-size: 16px !important;
  margin-top: 2px;
  text-align: left;
}
</style>
