<template>
<v-main>
    <v-toolbar class="white">
    <v-icon color="black" size="75">mdi-ember</v-icon>
    <v-spacer></v-spacer>
    <v-toolbar-items class="d-md-flex d-lg-flex d-xl-flex d-sm-none d-none">
      <v-btn
        plain
        text-center
        class="black--text ripple=false"
        v-for="link in links"
        :key="link.name"
        router
        :to="link.route"
        >{{ link.name }}</v-btn
      >
    </v-toolbar-items>
    <v-spacer></v-spacer>
    <v-btn
      elevation="4"
      class="red d-sm-none d-none d-md-flex d-lg-flex d-xl-flex"
      large
    >
      <v-icon large> mdi-logout </v-icon>
      <span>LoginOut</span>
    </v-btn>
    <v-btn
      @click="drawer = !drawer"
      text
      :ripple="false"
      class="d-md-none d-lg-none d-xl-none d-sm-flex"
    >
      <v-icon color="black">mdi-menu</v-icon>
    </v-btn>
  </v-toolbar>
  <v-navigation-drawer
    v-model="drawer"
    class="black text d-md-none d-lg-none d-xl-none d-sm-flex"
    fixed
    disable-resize-watcher
    disable-route-watcher
    hide-overlay
  
  >
    <v-list>
      <v-list-item v-for="link in links" :key="link.name" :to="link.route">
        <v-list-item-icon>
          <v-icon color="white">{{ link.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-title class="white--text">{{
          link.name
        }}</v-list-item-title>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</v-main>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          name: "Dashboard",
          route: "/",
          icon: "mdi-view-dashboard-variant-outline",
        },
        {
          name: "Employees",
          route: "/employees",
          icon: "mdi-account-multiple",
        },
        { name: "Tasks", route: "/tasks", icon: "mdi-calendar-check" },
      ],
      drawer: "false",
    };
  },
};
</script>

<style></style>
