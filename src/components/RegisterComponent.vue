    
<template>

    <v-content class="transparent">
        <v-layout align-center justify-center pa-1>
          <v-flex xs12 sm8 md4>
            <v-card>
              <v-toolbar dark color="primary">
                <v-toolbar-title>Resgister form</v-toolbar-title>
              </v-toolbar>
              <v-card-text>
                <v-form>
                  <v-text-field prepend-icon="person" name="Full Name" label="Full Name" type="text" required></v-text-field>
                  <v-text-field
                  prepend-icon="email"
                      label="E-mail"
                      v-model="email"
                      :rules="emailRules"
                      name="email"
                      type="email"
                      required
                     ></v-text-field>
                  <v-text-field id="password" prepend-icon="lock" name="password" label="Password" type="password" required></v-text-field>
                </v-form>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="primary">Register</v-btn>
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
   
    </v-content>

</template>

<script>
  export default {
    data: () => ({
      drawer: null,
      emailRules:[],
    }),
      watch: {
        e_Mail: function (mail) { // e_Mail is the exact name used in v-model
            if (mail !== '') {
                this.emailRules = [ v => (v.match(/^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/)) || 'Invalid Email address']
            } else if (mail === '') {
                this.emailRules = []
            }
        }
    },
    props: {
      source: String
    },
    
  }
</script>