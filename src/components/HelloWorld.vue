<template>
  <v-app
    dark
    id="inspire"
  >
    <v-navigation-drawer
      fixed
      :clipped="$vuetify.breakpoint.width > 1264"
      v-model="drawer"
      app
    >
      <v-list dense>
        <v-list-tile v-for="item in items" :key="item.text" @click="">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>
              {{ item.text }}
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-subheader class="mt-3 grey--text text--darken-1">SUBSCRIPTIONS</v-subheader>
        <v-list>
          <v-list-tile v-for="item in items2" :key="item.text" avatar @click="">
            <v-list-tile-avatar>
              <img :src="`https://randomuser.me/api/portraits/men/${item.picture}.jpg`" alt="">
            </v-list-tile-avatar>
            <v-list-tile-title v-text="item.text"></v-list-tile-title>
          </v-list-tile>
        </v-list>
        <v-list-tile class="mt-3" @click="">
          <v-list-tile-action>
            <v-icon color="grey darken-1">add_circle_outline</v-icon>
          </v-list-tile-action>
          <v-list-tile-title class="grey--text text--darken-1">Browse Channels</v-list-tile-title>
        </v-list-tile>
        <v-list-tile @click="">
          <v-list-tile-action>
            <v-icon color="grey darken-1">settings</v-icon>
          </v-list-tile-action>
          <v-list-tile-title class="grey--text text--darken-1">Manage Subscriptions</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar color="orange"  dense fixed clipped-left app>
      <v-toolbar-title
        :style="$vuetify.breakpoint.width > 1264 && 'width: 300px'"
        class="ml-0 pl-3"
        :class="$vuetify.breakpoint.width <= 1264 && 'pr-3'"
      >
        <v-toolbar-side-icon class="grey--text text--darken-2" @click.stop="drawer = !drawer"></v-toolbar-side-icon>
        <v-icon class="ml-3">apps</v-icon>
      </v-toolbar-title>
      <v-layout row align-center style="max-width: 650px">
        <v-text-field
          placeholder="Search..."
          single-line
          append-icon="search"
          :append-icon-cb="() => {}"
          class="grey--text"
          hide-details
        ></v-text-field>

      </v-layout>
      <v-icon class="ml-3">apps</v-icon>
      <v-icon class="ml-3">apps</v-icon>
    </v-toolbar>
    <v-content>
      <v-container fill-height class="grid-list-lg">
       
        <v-layout row wrap>
          <v-flex xs12 lg4>
            <single-card></single-card>
          </v-flex>
          <v-flex xs6 lg4>
            <single-card></single-card>
          </v-flex>
          <v-flex xs6 lg4>
            <single-card></single-card>
          </v-flex>
          <v-flex xs6 lg4>
            <single-card></single-card>
          </v-flex>
          <v-flex xs6 lg4>
            <single-card></single-card>
          </v-flex>
           
          <v-flex xs6 lg4>
            <dashboard-panel></dashboard-panel>
          </v-flex>
        </v-layout>
        
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  import SingleCard from './SingleCard.vue'
  import DashboardPanel from './DashboardPanel.vue'

  export default {
    components: {
      SingleCard,
      DashboardPanel
    },
    data: () => ({
      drawer: null,
      items: [
        { icon: 'trending_up', text: 'Most Popular' },
        { icon: 'subscriptions', text: 'Subscriptions' },
        { icon: 'history', text: 'History' },
        { icon: 'featured_play_list', text: 'Playlists' },
        { icon: 'watch_later', text: 'Watch Later' }
      ],
      items2: [
        { picture: 28, text: 'Joseph' },
        { picture: 38, text: 'Apple' },
        { picture: 48, text: 'Xbox Ahoy' },
        { picture: 58, text: 'Nokia' },
        { picture: 78, text: 'MKBHD' },
      ]
    }),
    props: {
      source: String
    }
    
  }
</script>

<style>
  .input-group__details:after {
    background-color: rgba(255, 255, 255, 0.32) !important;
  }
</style>