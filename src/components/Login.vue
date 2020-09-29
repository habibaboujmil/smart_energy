<template>
  <v-container class="container">
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col>
        <h1 class="display-2 font-weight-bold mb-3"
        style="font-family:sans-serif" >
          Welcome to Smart Energy Simulator
        </h1> 
      </v-col>
    </v-row >
      <v-card>
      <v-card-text>
        <v-form>
          <v-text-field 
            label="Username"
            prepend-icon="mdi-account-circle"
          />
          <v-text-field 
            :type="showPassword ? 'text' : 'password'" 
            label="Password"
            prepend-icon="mdi-lock"
            :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off' "
            @click:append="showPassword = !showPassword"
          />
        </v-form>
      </v-card-text>
      <v-divider></v-divider>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn 
        color="success" 
        width="100%"
        @click="login()"
        >Login</v-btn>
      </v-card-actions>
    </v-card>
    <v-row >
    <v-footer class="font-weight-medium" style="margin-top:20px" width="100%">
      <v-col
        class="text-center"
        cols="12"
      >Copyright@{{ new Date().getFullYear() }} — <strong>Smart Energy</strong>
      </v-col>
    </v-footer>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Login',

    data: () =>{
       return {
         form:{
            username: '',
            password: '',
          },
      showPassword: false
      } 
    },
    methods: {
      login() 
      {
        this.$router.push("/about");
      }
    }
  }
</script>

<style>
/* .container{
  background-color: ;
} */

</style>
