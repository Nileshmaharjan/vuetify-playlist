<template>
  <nav>
      <v-toolbar flat app>
        <v-toolbar-side-icon class="grey--text" @click="drawer = !drawer"></v-toolbar-side-icon>
        <v-toolbar-title class="text-uppercase grey--text"> 
            <span class="font-weight-light">Todo</span>
            <span>Ninja</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-title class="text-uppercase grey--text">
            <span>Sign Out</span>
            <v-icon right>exit_to_app</v-icon>
        </v-toolbar-title>

      </v-toolbar>


      <v-navigation-drawer v-model="drawer" app class="primary">
       <v-list>
           <v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
            <v-icon>{{link.icon}}</v-icon>
            <v-list-tile-content>
               <v-list-tile class="white--text">
                   {{link.text}}
               </v-list-tile>
           </v-list-tile-content>
        </v-list-tile>
          
       </v-list>
      </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
    data() {
        return {
            drawer: false,
             links: [
                { icon: 'dashboard', text: 'Dashboard', route: '/' },
                { icon: 'folder', text: 'My Projects', route: '/projects' },
                { icon: 'person', text: 'Team', route: '/team' },
      ]
        }
    }
}
</script>

<style>

</style>

