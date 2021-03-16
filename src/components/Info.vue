<template>
  <div class="info-hero">
    <v-container fluid class="mb-8 mt-2">
      <v-row no-gutters justify="center">
        <v-card
          class="ml-4 my-2"
          max-width="344"
          v-for="item in info"
          :key="item.header"
          :to="item.link"
          :title="item.header"
          cols="8"
          md="2"
        >
          <v-col>
            <v-card-actions>
              <v-btn text color="blue lighten-1 accent-4" :to="item.link">
                {{ item.link }}
              </v-btn>
            </v-card-actions>
            <v-card-text>
              <div class="pb-1">
                <v-icon>{{ item.icon }}</v-icon>
              </div>
              <div>
                <h3>{{ item.header }}</h3>
              </div>
              <div>
                <p>{{ item.infotext }}</p>
              </div>
            </v-card-text>
          </v-col>
        </v-card>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      info: [
        {
          icon: "mdi-layers-triple",
          header: "Buyer catalogue",
          infotext:
            "Create a search profile in our Buyer's Directory and be notified every time a home comes up for sale that matches your wishes.",
          link: "link 1",
        },
        {
          icon: "mdi-home",
          header: "myREC24",
          infotext:
            "Track your home sale, create a search profile in the buyer directory or save your favorite homes. You can also get messages and communicate directly with your real estate agent.",
          link: "link 2",
        },
        {
          icon: "mdi-cash-multiple",
          header: "Tailor-made sales",
          infotext:
            "It is often easy to give your home even more value before putting up for sale. It's small things that count - and they count more than you think!",
          link: "link 3",
        },
        {
          icon: "mdi-lightbulb-outline",
          header: "Sell your resident at REC24",
          infotext:
            "We will make an extra effort to provide you with good service and fast sales. At home, your home gets the best conditions for a good and efficient sale!",
          link: "link 4",
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>