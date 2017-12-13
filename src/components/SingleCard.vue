<template>
  <v-card class="rounded-all">
        <v-card-media
          src="src/assets/img/dealershipC.png"
          height="200px"
        >
        </v-card-media>
        <v-card-title primary-title class="text-xs-left">
          <div>
            <div class="headline">Tonys Auto Plaza </div>
            <span class="grey--text">123 Main Street, Kansas City MO 64114</span>
          </div>
        </v-card-title>
        <v-card-actions>
          <v-btn flat>Share</v-btn>
          <v-btn flat color="blue">Explore</v-btn>
          <v-spacer></v-spacer>
          <v-btn icon @click.native="show = !show">
            <v-icon>{{ show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
          </v-btn>
        </v-card-actions>
        <v-slide-y-transition>
          <v-card-text v-show="show">
            I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
          </v-card-text>
        </v-slide-y-transition>
      </v-card>
</template>

<script>
  export default {
    name: 'singleCard',
    data: () => ({
      
    }),
    props: {
      source: String
    }
  }
</script>

<style>
.rounded-all {
  border-radius: 10px 10px 10px 10px;
}
</style>