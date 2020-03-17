<template>
  <v-card class="pa-2 ma-2" color="light-green lighten-1">
    <p class="headline black--text">つくったもの</p>
    <v-list-item two-line v-for="app in apps" v-bind:key="app.name">
      <v-list-item-icon class="my-auto">
        <v-icon class="black--text">{{app.icon}}</v-icon>
      </v-list-item-icon>
      <v-list-item-content @click="open(app.link)">
        <v-list-item-title class="black--text">{{app.name}}</v-list-item-title>
        <v-list-item-subtitle class="black--text">{{app.description}}</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>
  </v-card>
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "App",
  data: () => ({
    apps: [
      {
        name: "たちみどろいど",
        description: "ニコ生の全部屋見れるコメビュ",
        platform: "Android",
        icon: "android",
        link:
          "https://play.google.com/store/apps/details?id=io.github.takusan23.tatimidroid"
      },
      {
        name: "つみとーも",
        description: "つりっくまのパクリゲー",
        platform: "Web系",
        icon: "web",
        link: "https://game.nicovideo.jp/atsumaru/games/gm13544?link_in=users"
      },
      {
        name: "NicoruCountFix",
        description: "ニコるくん9+直す拡張機能",
        platform: "Chrome Extension",
        icon: "extension",
        link:
          "https://chrome.google.com/webstore/detail/nicorucountfix/hfjbbhoeogmcfembakhiekefakkplbie?hl=ja"
      }
    ]
  }),
  methods: {
    open(link: string): void {
      window.open(link);
    }
  },
});
</script>
