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
      <div class="mt-6">
        <h2 class="motto">Summary</h2>

      <v-row>
        <v-col class="col-md-8">
          I am a 4th-year Software Engineering student. I am deeply interested in Software development and the
          Artificial intelligence area of the field. For the past 2 years, I have been interning for Software solution
          companies where I sharpen my skills and laid a strong foundation on Web development and Machine learning applications.
          I am excited and eager to learn and explore more about AI, especially on Computer Vision. My interest other
          than programming is making 3D animations, playing basketball, watching biography movies, and charity programs.
        </v-col>
      </v-row>
      </div>

      <div class="mt-5 col-md-8">
        <h2 class="motto">Papers</h2>
        <p>Coming soon in the Near future</p>
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
                  <strong>Research Assistant at Umich</strong>
                </div>
                <div>The Lab focuses on Computer Vision, understanding the world in terms of Physical property and Functional property.
                  I worked on Understanding scene using human as a ruler, by training a model of Depth estimation and Floor prediction</div>
              </div>
            </v-timeline-item>

            <v-timeline-item
              small
            >
              <div>
                <div class="font-weight-normal">
                  <strong>Research Assistant at Umich</strong>
                </div>
                <div>The Lab focuses on Computer Vision, understanding the world in terms of Physical property and Functional property.
                  I worked on Understanding scene using human as a ruler, by training a model of Depth estimation and Floor prediction</div>
              </div>
            </v-timeline-item>

            <v-timeline-item
              small
            >
              <div>
                <div class="font-weight-normal">
                  <strong>Research Assistant at Umich</strong>
                </div>
                <div>The Lab focuses on Computer Vision, understanding the world in terms of Physical property and Functional property.
                  I worked on Understanding scene using human as a ruler, by training a model of Depth estimation and Floor prediction</div>
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
