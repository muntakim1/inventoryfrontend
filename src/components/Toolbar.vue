<template>
  <nav>
    <v-toolbar tabs app>
      <v-toolbar-side-icon @click="drawer=!drawer"></v-toolbar-side-icon>

      <v-toolbar-title><span class="cyan--text">Hunan</span>Denim</v-toolbar-title>

      <v-spacer></v-spacer>
      <div v-if="showSearch">
        <v-text-field name="Search" label="Search" single-line></v-text-field>
      </div>
      <v-btn icon @click="showSearch=!showSearch">
        <v-icon>search</v-icon>
      </v-btn>

      <v-menu bottom left>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>more_vert</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-tile @click="1">
            <v-list-tile-action>
              <v-icon>person</v-icon>
            </v-list-tile-action>
            <v-list-tile-title>Profile</v-list-tile-title>
          </v-list-tile>
          <v-list-tile @click="1">
             <v-list-tile-action>
              <v-icon>arrow_forward</v-icon>
            </v-list-tile-action>
            <v-list-tile-title>Logout</v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-menu>

    </v-toolbar>
    
    <v-navigation-drawer v-model="drawer"  value="true" app dark fixed>
      <v-toolbar flat class="transparent">
        <v-list class="pa-0">
          <v-list-tile avatar>
            <v-list-tile-avatar>
              <img :src="userprofile">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>{{UserName}}</v-list-tile-title>
              <v-list-tile-sub-title>Welcome to HunanDenim</v-list-tile-sub-title>
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
          <v-list-tile v-for="(CRM, i) in CRM" :key="i" @click="1"  router :to='CRM[2]'>
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
          <v-list-tile v-for="(bill, i) in Bill" :key="i" @click="1">
            <v-list-tile-title v-text="bill[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="bill[1]"></v-icon>
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
  </nav>
</template>

<script>
export default {
    data(){
        return{
          themeChangeData:'',
           drawer: false,
            showSearch: false,
            menudrawer: false,
            userprofile:"https://scontent.fdac7-1.fna.fbcdn.net/v/t1.0-9/51078362_2243788455839300_7046474069104918528_n.jpg?_nc_cat=105&_nc_oc=AQkp6MkyMOT9cgnBuqv3YNES9PNEengORM4lgB5-AuL3XCfZl6wbfi3hFbO7kL3vLgc&_nc_ht=scontent.fdac7-1.fna&oh=b30dba13be61ecfe96b0bc92a0994dbb&oe=5DA407B7",
            UserName:"Admin",
             CRM: [
            ['Add New Client', 'person_outline','addclient'],
            ['Add Client Group', 'people_outline','addclient'],
            ['Client List', 'people_outline','addclient'],
            ['Add Supplier', 'person_outline','addclient'],
            ['Add Supplier Group', 'people_outline','addclient'],
            ['Supplier List', 'people_outline','addclient'],
           
            ],
            Transaction:[
              ['Recieve','radio_button_checked'],
              ['Expense','radio_button_checked'],
              ['Supplier Payment','radio_button_checked'],
              ['Transfer','radio_button_checked'],
              ['Account Balances','radio_button_checked'],
              ['Profit','radio_button_checked'],
              ['Balance Sheet','radio_button_checked'],
              ['Account Statement','radio_button_checked'],
              ['Money Receipt','radio_button_checked'],
              ['Account Create','radio_button_checked'],
              ['Account List','radio_button_checked'],

            ],
            Bill:[
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
