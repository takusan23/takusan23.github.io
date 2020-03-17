<template>
  <v-app>
    <v-content>
      <v-container class="fill-height" fluid>
        <v-col>
          <Profile></Profile>
          <AppList></AppList>
        </v-col>
      </v-container>
    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import Profile from "./components/Profile.vue";
import AppList from "./components/AppList.vue";

export default Vue.extend({
  name: "App",

  components: {
    Profile,
    AppList,
  },

  data: () => ({
    //
  })
});
</script>
