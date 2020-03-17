<template>
  <v-card class="pa-2 ma-2" color="light-blue accent-1 black--text">
    <v-row class="ma-2">
      <img :src="icon" width="50" height="50" class="my-auto" />
      <v-col>
        <p class="headline">{{name}} @{{id}}</p>
        <p>Androidアプリ作ったりTypeScript書いてたりする</p>
        <p>Vue.js と TypeScript と Vuetify で作った</p>
        <v-row class="ma-2">
          <v-btn class="ma-2" color="blue-grey white--text" @click="open(githubLink)">
            <v-icon>code</v-icon>Github
          </v-btn>
          <v-btn class="ma-2" color="light-blue white--text" @click="open(mastodonLink)">
            <v-icon>create</v-icon>Mastodon
          </v-btn>
        </v-row>
      </v-col>
    </v-row>
  </v-card>
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "App",
  data: () => ({
    name: "たくさん",
    id: "takusan_23",
    mastodonLink: "https://best-friends.chat/@takusan_23",
    githubLink: "https://github.com/takusan23",
    icon:
      "https://media.best-friends.chat/accounts/avatars/000/020/498/static/bc0bd14abb0bb063.png"
  }),
  methods: {
    open(link: string): void {
      window.open(link);
    }
  }
});
</script>
