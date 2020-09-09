<template>
  <v-container>
    <v-data-table
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        headers: [
          {text: 'ID', value:'id'},
          { text: 'Name', value: 'name' },
          { text: 'Phone Number', value: 'phone' },
        ],
        desserts: [],
      }
    },

    created(){
      this.axios.get(process.env.VUE_APP_API_URL+'/customer').then((response) => {
        this.desserts = response.data;
      })
    }
  }
</script>
