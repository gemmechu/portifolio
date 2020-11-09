<template>
  <div>
    <banner
      img-width="18rem"
      title="Acivities"
      description=""
      img="./news.svg"
    />

    <v-container class="my-15">
      <h2 class="display-1">
        Latest Updates
      </h2>
      <v-divider class="mt-2" />
      <template v-for="post in posts">
        <v-hover v-slot="{ hover }" :key="post.id">
          <nuxt-link :to="post.link">
            <v-card
              max-width="800"
              class="mx-auto my-4"
              outlined
              tile
              :elevation="hover ? 12 : 0"
              :class="{ 'on-hover': hover }"
            >
              <v-row class="mx-2 align-center">
                 <v-col cols="12">
                  <v-card-title class="justify-space-between">
                    <h2>{{ post.title }}</h2>
                    <small>{{ post.date }}</small>
                  </v-card-title>
                  <v-divider />

                  <v-card-text>
                    <div>
                      {{ post.preview }}
                    </div>
                  </v-card-text>
                </v-col>

                <v-col cols="12" px-4 v-if="post.video == 0">
                  <v-img  :src="post.image" />
                </v-col>
                <v-col cols="12" px-4 v-if="post.video == 1">
                  <iframe  width="100%" height="310px" :src="post.src" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
                </v-col>


              </v-row>
            </v-card>
          </nuxt-link>
        </v-hover>
      </template>
    </v-container>
  </div>
</template>

<script>
import Banner from "@/components/Core/TextOnlyBanner";
export default {
  components: {
    Banner
  },
  data() {
    return {
      model: 0,
      colors: ["primary", "secondary", "yellow darken-2", "red", "orange"],
      posts: [
        {
          id: 1,
          video: 1,
          link:"aura.engin.umich.edu/home",
          title: "AURA Final presentation - Umich",
          date: "Oct 2, 2020",
          image:"",
          src: "https://www.youtube.com/embed/0EUMW2yIA_0",
          preview:
            "AURA program is African Undergraduate Research Adventure, it is formed by Umich and AAiT partnership for 4th year AAiT students explore the research world at university of Michigan."
        },

        {
          id: 2,
          video: 0,
          link:"https://twitter.com/TTAfroFM/status/1255544263338872834",
          title: "AfroFm 105.3 <> Eskalate interview",
          date: "April 15, 2020",
          image:"https://pbs.twimg.com/media/EWyW0tmX0AAZaIP?format=jpg&name=small",
          src: "",
          preview:
            "In response to COVID-19 pandemic Eskalate responded  by building symptom tracker the application can be found on http://tracksym.app/"
        },
        {
          id: 3,
          video: 0,
          link:"eskalate.io",
          title: "Co-founder at Eskalate",
          date: "March, 2020",
          image:"https://res.cloudinary.com/eskalate/image/upload/v1596886461/gallery/IMG_20200306_150536_etyrgf.jpg",
          src: "",
          preview:
            "Eskalate's mission is to be a digital bridge between underdeveloped and developed world. We aim to maximize social impact, not profit"
        },

      ]
    };
  }
};
</script>

<style scoped>
.v-card {
  transition: opacity 0.4s ease-in-out;
}

.v-card:not(.on-hover) {
  opacity: 0.9;
}

a {
  text-decoration: none;
}

h2:hover {
  color: #1084cb;
}
</style>
