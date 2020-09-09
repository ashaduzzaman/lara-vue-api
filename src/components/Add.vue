<template>
  <v-form
    ref="form"
  >
    <v-text-field
      v-model="data.name"
      :counter="10"
      :rules="nameRules"
      label="Name"
      required
    ></v-text-field>

    <v-text-field
      v-model="data.phone"
      label="Phone"
      required
    ></v-text-field>

    <v-btn
      color="success"
      @click="submit"
    >
      Submit
    </v-btn>
  </v-form>
</template>

<script>
  export default {
    data: () => ({
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      data: {
        name: '',
        phone: '',
      }
    }),

    methods: {
      submit () {
        //   console.log('saved');
          this.axios.post(process.env.VUE_APP_API_URL+'/customer', this.data).then((response) => {
              console.log('Successfully saved');
              console.log(response);
          })
      },
    },
  }
</script>