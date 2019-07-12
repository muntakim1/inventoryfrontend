<template>
  <v-app>
    <v-layout column>
      
    
   <div v-if="$route.path === '/login' ">
      </div>
      <div v-else>
        <ToolBar />
      </div>
       <v-content>
        <router-view></router-view>
      </v-content>

     </v-layout>
  </v-app>
</template>

<script>
import ToolBar from './components/Toolbar'

export default {
  name: 'App',
  components: {
  ToolBar
  },
  data () {
    return {
      //
    }
  }
}
</script>
