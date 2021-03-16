<template>
  <div class="condo">
    <v-container fluid class="ml-0 mt-0 mb-0 mr-0 pa-0 lightbgoverlay">
      <v-row no-gutters class="text-center">
        <v-col>
          <h2 class="headingcolor headingsale mt-2">Residents for sale</h2>
        </v-col>
      </v-row>
      <v-row no-gutters>
        <v-col cols="12" md="7">
          <v-bottom-navigation
            v-model="value"
            class="v-bottom-navigation-new theme--light-bottom-navigation-new"
            color="primary"
          >
            <v-btn value="all">
              <span>All</span>
              <v-icon>mdi-home</v-icon>
            </v-btn>
            <v-btn value="saved">
              <span>Saved</span>
              <v-icon>mdi-heart</v-icon>
            </v-btn>
            <v-btn value="latest">
              <span>Latest Seen</span>
              <v-icon>mdi-history</v-icon>
            </v-btn>
            <v-btn value="sort">
              <span>Sort</span>
              <v-icon>mdi-sort</v-icon>
            </v-btn>
          </v-bottom-navigation>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid class="lightbgoverlay pb-8">
      <v-row no-gutters justify="center">
        <v-card
          class="ml-4 my-2"
          max-width="344"
          v-for="item in condo"
          :key="item.id"
          cols="8"
          md="2"
        >
          <v-col>
            <v-card-actions class="action-card-header">
              <v-btn value="saved" text>
                <v-icon>mdi-heart</v-icon>
              </v-btn>
              <div class="energylabel font-weight-bold">
                  <span :title="item.energy">{{ item.energy }}</span>
                </div>
            </v-card-actions>
            <router-link :to="item.link" class="none">
              <v-img
                class="white--text align-end"
                height="200px"
                src="https://cdn.pixabay.com/photo/2018/07/27/00/32/apartment-3564955_960_720.jpg"
                :title="item.header"
              >
              <v-card-title>New</v-card-title>
              </v-img>
            </router-link>
            <v-card-text>
              <div>
                <router-link :to="item.link" :title="item.header" class="none linkblack">
                <h3>{{ item.header }}</h3>
                </router-link>
              </div>
              <div>
                <p class="pa-0 ma-0">{{ item.infopost }}</p>
              </div>
              <div>
                <p class="pa-0 ma-0">{{ item.type }}</p>
              </div>
              <div class="costinfo mt-2">
                  <p class="pa-0 ma-0 pt-1">{{ item.use }} {{ currency }} {{ item.useamout }} <span class="float-right font-weight-bold"> {{ currency }} {{ item.price }} </span></p>
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
      value: "",
      currency: "kr.",
      condo: [
        {
          id: "1",
          header: "Test Street 69",
          infopost: "7000 City",
          type: "Condo",
          use: "Ownership costs",
          useamout: "2.000",
          price: "5.000.000",
          energy: "C",
          link: "link 1",
        },
        {
          id: "2",
          header: "Test Street 69",
          infopost: "9000 City",
          type: "Villa",
          use: "Ownership costs",
          useamout: "1.500",
          price: "8.000.000",
          energy: "A",
          link: "link 1",
        },
        {
          id: "3",
          header: "Test Street 69",
          infopost: "7000 City",
          type: "Condo",
          use: "Ownership costs",
          useamout: "2.000",
          price: "5.000.000",
          energy: "C",
          link: "link 1",
        },
        {
          id: "4",
          header: "Test Street 69",
          infopost: "9000 City",
          type: "Villa",
          use: "Ownership costs",
          useamout: "1.500",
          price: "8.000.000",
          energy: "A",
          link: "link 1",
        },
      ],
    };
  },
};
</script>

<style scoped>
.v-card__title {
  padding: 0px !important;
  background-color: #003761;
  justify-content: center;
  opacity: 95%;
}

.action-card-header {
    justify-content: end;
}

.energylabel {
    background-color: #d09f26;
    width: 20px;
    text-align: center;
    border-radius: 3px;
    color: #fff;
}

.costinfo {
    border-top: 1px solid #000;
}
</style>