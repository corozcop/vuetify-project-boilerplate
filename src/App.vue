<template>
  <v-app>
    <v-navigation-drawer temporary v-model="sideNav" fixed app>
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :key="i"
          value="true"
        >
          <v-list-tile-action>
            <v-icon light>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar app dark class="primary">
      <v-toolbar-side-icon @click.stop="sideNav = !sideNav"
      class="hidden-sm-and-up">

      </v-toolbar-side-icon>

      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn flat v-for="(item, i) in items" :key="i">
          <v-icon left dark>{{ item.icon }}</v-icon>
          {{ item.title }}
        </v-btn>

      </v-toolbar-items>

    </v-toolbar>
    <main>
      <router-view></router-view>
    </main>

    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data: function () {
      return {
        sideNav: false,
        fixed: true,
        items: [
          {icon: 'account_balance_wallet', title: 'Account'},
          {icon: 'rounded_corner', title: 'Reports'}
        ],
        title: 'Web Application'
      }
    }
  }
</script>
