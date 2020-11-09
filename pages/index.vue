<template>
  <div>
    <Banner />
    <navigation-drawer
      v-if="drawer"
      :drawer="drawer"
      :user-id="userId"
      @toggle-drawer="drawer = !drawer"
    />
    <v-container class="grey lighten-5">
      <div class="mt-6 col-md-8">
        <h2 class="motto">Summary</h2>

      <v-row>
        <v-col class="">
          I am a 4th-year Software Engineering student. I am deeply interested in Software development and the Artificial intelligence area of the field. For the past 3 years, I work on Web and mobile Applications, 3D animation, Computer Vision projects with some of the most interesting people. I am excited and eager to learn and explore more about AI, especially on Computer Vision. As a hobby, I like to play basketball, watch biography movies, and charity programs.
        </v-col>
      </v-row>
      </div>

      <div class="mt-5 col-md-8">
        <h2 class="motto">Papers</h2>
        <p>Coming soon in the near future</p>
      </div>

      <div class="mt-5 col-md-8">
        <h2 class="motto">Expiriances</h2>
        <v-timeline
            align-top
            dense
          >
            <v-timeline-item
              small
            >
              <div>
                <div class="font-weight-normal">
                  <strong>Research Assistant at University of Michigan</strong>
                </div>
                <div>The Lab focuses on Computer Vision, understanding the world in terms of Physical property and Functional property.
                  I worked on Understanding scene using human as a ruler, by training a model of Depth estimation and Floor prediction
                </div>
                <iframe class ="my-3" width="90%" height="310px" src="https://www.youtube.com/embed/0EUMW2yIA_0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
              </div>
            </v-timeline-item>

            <v-timeline-item
              small
            >
              <div>
                <div class="font-weight-normal">
                  <strong>Co-founder at Eskalate</strong>
                </div>
                <div>Is a company based in US founded by group of people from Ethiopia, Turkey and US.
                  We focus on building a bridge between developing countries and
                  Silicon Valley and Developing software Applications. I work as web developer and in business team.
                  <v-btn color="primary" text href="eskalate.io"> Link</v-btn>
                  </div>
              </div>

            </v-timeline-item>

            <v-timeline-item
              small
            >
              <div>
                <div class="font-weight-normal">
                  <strong>ITSC-INSPIRE President</strong>
                </div>
                <div>ITSC-INSPIRE is the biggest student organization within AAIT, we organize hackathon, seminars and tutorials
                  in addition we sponsored 1st Ai in Ethiopia conference. Our core mission is experience sharing and Helping each other.

                <v-img src="twitter_ceo.jpg" width="90%" class="my-3"></v-img>
                </div>
              </div>
            </v-timeline-item>
          </v-timeline>
      </div>

    </v-container>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Banner from "@/components/Core/Banner";

export default {
  components: {
    Banner,
    NavigationDrawer: () => import("~/components/Teams/NavigationDrawer")
  },
  data() {
    return {
      drawer: null,
      userId: null,
      baseUrl: process.env.baseUrl
    };
  },
  computed: {
    ...mapGetters("team", ["getTeamMembers"])
  },
  created() {
    this.$store.dispatch("team/fetchMembers");
  }
};
</script>
