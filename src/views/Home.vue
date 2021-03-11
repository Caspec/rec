<template>
  <div class="home">
    <v-container fluid class="ma-0 pa-0">
      <v-row>
        <v-col>
          <v-img
            src="@/assets/girl-1920.jpg"
            alt="Buy your new dream"
            class="hero"
          >
            <v-row>
              <v-col>
                <div class="d-flex flex-coldir-herooverlay">
                  <div class="d-flex align-center justify-center">
                    <v-card flat color="transparent">
                      <v-card-text class="white--text font-weight-black"
                        ><h2 class="hero__text">My real estate agent</h2>
                      </v-card-text>
                      <v-card-subtitle class="mt-5 sub"
                        ><h2 class="hero__subtext">
                          Be Home with a name you can trust.
                        </h2>
                      </v-card-subtitle>
                    </v-card>
                  </div>
                </div>
              </v-col>
            </v-row>
            <v-row>
              <v-col>
                <div class="d-flex fill-height flex-coldir-overlay">
                  <div class="d-flex fill-height align-center justify-center">
                    <v-card flat color="transparent">
                      <v-card-text class="white--text ml-2">
                        <h2 class="overlay__text">Thinking of selling?</h2>
                      </v-card-text>
                      <v-card-subtitle class="ml-4">
                        <v-btn
                          x-large
                          color="success"
                          class="overlay__btn font-weight-bold"
                          to="/about"
                          title="Order free sales assessment"
                        >
                          Order free sales assessment
                        </v-btn>
                      </v-card-subtitle>
                    </v-card>
                  </div>
                </div>
              </v-col>
            </v-row>
          </v-img>
        </v-col>
      </v-row>
    </v-container>
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
// @ is an alias to /src

export default {
  name: "Home",
  data() {
    return {
      value: "",
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
.hero {
  height: 950px;
}

.flex-coldir-herooverlay {
  flex-direction: column;
  position: relative;
  top: 520px;
  font-size: 10vw;
}

.flex-coldir-overlay {
  flex-direction: column;
  position: relative;
  top: 675px;
  background-color: rgba(16, 39, 59, 0.85);
}

.hero__text {
  font-size: 6em;
  text-align: center;
}

.hero__subtext {
  font-size: 2em;
  color: #ededed;
  text-align: center;
}

.sub {
  padding-left: 20px;
}

.overlay__text {
  font-size: 2.5em;
}

.overlay__btn {
  text-transform: unset !important;
}

@media screen and (max-width: 768px) {
  .flex-coldir-herooverlay {
    top: 120px;
    right: 0px;
  }
  .flex-coldir-overlay {
    display: none;
  }
  .hero {
    height: auto;
  }
  .hero__text {
    font-size: 10vw;
    color: #fff;
  }
  .hero__subtext {
    font-size: 2em;
    color: #ededed;
  }
  .sub {
    padding-left: 10px;
  }
  .v-card__subtitle {
    margin-top: 0px !important;
  }
}
</style>