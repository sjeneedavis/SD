<template>
  <v-app id="inspire">
    <v-navigation-drawer
    v-model="drawer"
    app>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            FLX QA Site
          </v-list-item-title>
          <v-list-item-subtitle>
            Navigation Menu
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
   
    

      <v-divider></v-divider>
    
      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="#102830"
      dark
      prominent
      
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), #00d47e"
        ></v-img>
      </template>

      <v-app-bar-nav-icon @click="drawer=!drawer">
        
      </v-app-bar-nav-icon>

      <v-app-bar-title></v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

  <v-main>
    <div>
    <v-breadcrumbs :items="items">
      <template v-slot:divider>
        <v-icon>mdi-forward</v-icon>
      </template>
    </v-breadcrumbs>

  
  </div>
  <router-view></router-view>
  </v-main>
  </v-app>


</template>

<script>
  export default {
    data: () => ({ 
      drawer: null,
      items: [
          { title: 'Mobile Apps', icon: 'mdi-cellphone', to:'/apps' },
          { title: 'Websites', icon: 'mdi-open-in-app', to:'/websites' },
          { title: 'Test Plans', icon: 'mdi-notebook-multiple', to:'/testplans' },
          { title: 'Devices', icon: 'mdi-tablet-cellphone', to:'/devices' },
          { title: 'Admin', icon: 'mdi-playlist-edit', to:'/admin' },
          { title: 'Logout', icon: 'mdi-exit-to-app', to:'/logout' },
        ], 
      }),
  }
</script>