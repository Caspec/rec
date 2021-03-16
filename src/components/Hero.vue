<template>
    <div class="hero">
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
    </div>
</template>

<script>
export default {
    
}
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