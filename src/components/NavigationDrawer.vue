<template>
    <div>
        <v-navigation-drawer v-model="drawer" stateless value="true" dark>
      <v-toolbar flat class="transparent">
        <v-list class="pa-0">
          <v-list-tile avatar>
            <v-list-tile-avatar>
              <img :src="userprofile">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>{{UserName}}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-toolbar>
      <v-divider></v-divider>
      <v-list>
        <v-list-tile href="/" @click="1">
          <v-list-tile-action>
            <v-icon>dashboard</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Dashboard</v-list-tile-title>
        </v-list-tile>

        <v-list-group prepend-icon="rate_review" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>CRM</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(CRM, i) in CRM" :key="i" @click="1">
            <v-list-tile-title v-text="CRM[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="CRM[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>

        <v-list-group prepend-icon="laptop" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Transactions</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(transaction, i) in Transaction" :key="i" @click="1">
            <v-list-tile-title v-text="transaction[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="transaction[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>

        <v-list-group prepend-icon="insert_chart" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Bill/Invoices</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(transaction, i) in Transaction" :key="i" @click="1">
            <v-list-tile-title v-text="transaction[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="transaction[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>

        <v-list-group prepend-icon="local_grocery_store" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Office Purchase</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(transaction, i) in Transaction" :key="i" @click="1">
            <v-list-tile-title v-text="transaction[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="transaction[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>
        
        <v-list-group prepend-icon="filter_none" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Products</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(transaction, i) in Transaction" :key="i" @click="1">
            <v-list-tile-title v-text="transaction[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="transaction[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>
        <v-list-group prepend-icon="bug_report" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Due Reports</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(transaction, i) in Transaction" :key="i" @click="1">
            <v-list-tile-title v-text="transaction[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="transaction[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>
        <v-list-group prepend-icon="bug_report" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Sales Reports</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(transaction, i) in Transaction" :key="i" @click="1">
            <v-list-tile-title v-text="transaction[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="transaction[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>
        <v-list-group prepend-icon="bug_report" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Deposit Reports</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(transaction, i) in Transaction" :key="i" @click="1">
            <v-list-tile-title v-text="transaction[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="transaction[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>
        <v-list-group prepend-icon="bug_report" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Expense Reports</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-tile v-for="(transaction, i) in Transaction" :key="i" @click="1">
            <v-list-tile-title v-text="transaction[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="transaction[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>
        <v-list-group prepend-icon="settings" value="true">
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Settings</v-list-tile-title>
            </v-list-tile>

          </template>
          <v-list-group
          sub-group
          no-action
        >
          <template v-slot:activator>
            <v-list-tile>
              <v-list-tile-title>Themes</v-list-tile-title>
            </v-list-tile>
          </template>
          <v-list-tile
            v-for="(themes, i) in Themes"
            :key="i"
            @click="1"
          >
            <v-list-tile-title v-text="themes[0]"></v-list-tile-title>
            <v-list-tile-action>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
    </div>
</template>


<script>
export default {
    data(){
        return{
          themeChangeData:'',
           drawer: false,
            showSearch: false,
            menudrawer: false,
            userprofile:"https://randomuser.me/api/portraits/men/85.jpg",
            UserName:"Admin",
             CRM: [
            ['Management', 'people_outline'],
           
            ],
            Transaction:[
              ['New Invioces','radio_button_checked'],
              ['Invioces List','radio_button_checked'],
              ['Invioces Item List','radio_button_checked'],

            ],
            Themes:[
              ['Blue',],
              ['Red'],
              ['Green']
            ],
            items: [
               { title: 'Profile', },
                { title: 'Logout' ,},
            ]
        }
    },
    
}
</script>
