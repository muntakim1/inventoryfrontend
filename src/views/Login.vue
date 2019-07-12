<template>
  <v-layout row>
          <v-content align-center justify-center>
      <v-container grid-list-lg>
          <v-tabs
          v-model="tabs"
          fixed-tabs
          color="transparent"
          slider-color="white"
      >
        <v-tab class="white">
            LOGIN
        </v-tab>
        <v-tab-item>
          
               <LoginComponent/>
          
        </v-tab-item>
        <v-tab class="white">
            Register
        </v-tab>
        <v-tab-item>
        
               <RegisterComponent/>
      
        </v-tab-item>
      </v-tabs>
      </v-container>
          </v-content>
  </v-layout>
</template>
<script>
import LoginComponent from '../components/LoginComponent'
import RegisterComponent from '../components/RegisterComponent'
  export default {
      components:{
          LoginComponent,
          RegisterComponent
      },
    data () {
      return {
        tabs: null,
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
      }
    }
  }
</script>

