<template>
  <!-- <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
    </v-app-bar>

    <v-main>
      <HelloWorld/>
    </v-main>
  </v-app> -->
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/add">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',
  data: () => ({
    //
  }),
};
</script>
