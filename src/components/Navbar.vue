<template>
  <div>
    <v-app-bar app color="red darken-4">
      <v-toolbar-title class="white--text">
          <router-link
          to="/"
          class="white--text logotext"
          title="Real Estate Commerce 24"
          ><h1 :class="[$vuetify.breakpoint.mdAndUp ? 'display-desktop' : 'display-mobile']">Real Estate Commerce 24</h1></router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-form>
        <v-autocomplete
          chips
          clearable
          hide-details
          hide-selected
          item-text="name"
          item-value="estate"
          label="Quick search for a real estate"
          solo
          class="light-red lighten-5 mr-3 hidden-xs-only"
          color="red darken-4"
        >
        </v-autocomplete>
      </v-form>
      <v-btn icon class="white--text ml-3" to="/about" title="My REC24">
        <v-icon>mdi-account-outline</v-icon>
      </v-btn>
      <v-app-bar-nav-icon
        class="white--text"
        @click="drawer = true"
        title="Menu"
      >
     </v-app-bar-nav-icon>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" absolute temporary right>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="deep-red--text text--accent-4"
        >
          <v-list-item two-line v-for="item in menu" :to="item.route" :key="item.title">
            <v-list-item-content>
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
            <div v-if="item.submenu">
            <v-list-item-subtitle v-for="sub in item.submenu" :key="sub.title">
              {{ sub.title}}
            </v-list-item-subtitle>
            </div>
        </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      drawer: false,
      group: null,
      menu: [
        { icon: "mdi-home", title: "Home", route: "/" },
        { icon: "mdi-home-search", title: "Search residential", route: "2" },
        { icon: "mdi-account-search", title: "Find real estate agent", route: "2" },
        { 
          icon: "mdi-home-plus", 
          title: "Buy residential", 
          route: "2",
          submenu: [
            { icon: "mdi-account-multiple", title: "Parent buy", route: "2" },
            { icon: "mdi-home-outline", title: "Summer residential", route: "2" },
            { icon: "mdi-folder-home", title: "Buyer catalogue", route: "2" },
            { icon: "mdi-layers-triple", title: "Buyer advice", route: "2" }
          ]
        },
        { 
          icon: "mdi-home-minus", 
          title: "Sell residential", 
          route: "2",
          submenu: [
            { icon: "mdi-information", title: "Why choose REC24?", route: "2" },
            { icon: "mdi-home-city", title: "Sale of residential projects", route: "2" },
            { icon: "mdi-home-outline", title: "Sale of summer residential", route: "2" },
            { icon: "mdi-lightbulb-on", title: "99 free sales tips", route: "2" }
          ] 
        },
        { icon: "mdi-home-group", title: "Projectsales & rentals", route: "2" },
        { 
          icon: "mdi-cash-multiple", 
          title: "Condos", 
          route: "2",
          submenu: [
            { icon: "mdi-information", title: "What is a Condo?", route: "2" },
            { icon: "mdi-home-city", title: "Your local real estate office", route: "2" },
            { icon: "mdi-home-outline", title: "Sell of condos", route: "2" },
            { icon: "mdi-account-tie", title: "Tailor-made sales", route: "2" }
          ]
        },
        { icon: "mdi-new-box", title: "News about the market", route: "2" },
        { 
          icon: "mdi-information", 
          title: "About REC24", 
          route: "about",
           submenu: [
            { icon: "mdi-newspaper-variant", title: "Brochures", route: "2" },
            { icon: "mdi-briefcase", title: "Job", route: "2" },
            { icon: "mdi-shield-lock", title: "Privacy policy", route: "2" }
          ] 
        },
        { icon: "mdi-home-modern", title: "Homes for rent", route: "2" },
        { icon: "mdi-login", title: "Login REC24", route: "2" },
        { icon: "mdi-account-group", title: "Book free sales assessment", route: "2" },
      ],
    };
  },
};
</script>

<style>
.logotext {
  text-decoration: none;
  font-size: 1.4em;
}

.display-desktop {
  font-size: 1.8rem;
}

.display-mobile {
  font-size: 1.4rem;
  margin-right: 50px;
}
</style>