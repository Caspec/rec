<template>
  <v-footer color="grey lighten-3" padless>
    <v-container>
    <v-row no-gutters justify="center">
      <v-col class="my-2 pl-2 ml-4 footer_column" cols="8" md="2" v-for="item in footer" :key="item.header">
        <h4 class="font-weight-medium footer_title">{{ item.header }}</h4> 
        <v-row no-gutters v-for="linkitem in item.link" :key="linkitem.text">
          <v-col>{{ linkitem.text}}</v-col>
        </v-row>
      </v-col>
    </v-row>
    </v-container>
    <v-container fluid>
      <v-row>
        <v-col class="grey lighten-2 py-4 text-center black--text" cols="12">
        {{ new Date().getFullYear() }} — <strong>Real Estate Commerce 24</strong>
      </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      footer: [
        { header: "Find real estate agent", link: [ 
          { text: "Agent1", route: "Agent1"}, { text: "Agent2", route: "Agent2"}, { text: "Agent3", route: "Agent3"}
        ]
        },
        { 
          header: "Buy and sell residential", link: [ 
        { text: "Project sales & rentals", route: "Project sales & rentals"}, { text: "REC24 buyer advice", route: "REC24 buyer advice"}, { text: "Parental purchase", route: "Parental purchase"}
        ] 
        },
        { 
          header: "About the residential market", link: [ 
        { text: "Residential news", route: "Residential news"}, { text: "Subscribe to newsletter", route: "Subscribe to newsletter"}, { text: "Press", route: "Press"}
        ] 
        },
        { 
          header: "About REC24", link: [ 
        { text: "About REC24", route: "About REC24"}, { text: "Job at REC24", route: "Job at REC24"}, { text: "Become a franchisee", route: "Become a franchisee"}
        ] 
        },
      ]
    }
  },
};
</script>

<style scoped>
.footer_column {
  border-top: 1px solid #b2aeae;
}

.footer_title {
  font-size: 1.2em;
}
</style>