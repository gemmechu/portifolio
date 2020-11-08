<template>
  <v-footer padless>
    <v-card flat tile class="white text-center">
      <v-card-text style="width: 100vw">
        <v-container>
         <p class="blackish footer-texts">
                © Copyright 2020 A2SV NPO. All rights reserved.
          </p>
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
