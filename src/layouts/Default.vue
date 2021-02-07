<template>
  <v-app>
    <v-navigation-drawer permanent>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Application
          </v-list-item-title>
          <v-list-item-subtitle>
            subtext
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
    <v-main>
      <v-container>
        <slot/>
      </v-container>
    </v-main>
  </v-app>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
  export default {
    data () {
      return {
        items: [
          { title: 'Contact', icon: 'mdi-account' },
          { title: 'Projects', icon: 'mdi-briefcase' },
          { title: 'Education', icon: 'mdi-book-education' },
          { title: 'Contact', icon: 'mdi-phone' },
        ],
        right: null,
      }
    },
  }
</script>

<style>
  .v-application--wrap{
    flex-direction: row;
  }
</style>
