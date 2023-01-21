<template>
  <v-app id="inspire" >

    <v-navigation-drawer
      app
      elevation="7"
      permanent
      color="primary"
    >
      <v-sheet
        class="pa-4"
        color="primary"
        dark
      >
        <v-avatar
          class="mb-4"
          size="64"
        ></v-avatar>

        <div>john@vuetifyjs.com</div>
      </v-sheet>

      <v-divider></v-divider>

      <v-list dark>
        <v-list-item
          v-for="[icon, text,url] in links"
          :key="icon"
          link
          :to="url"
        >
          <v-list-item-icon>
            <v-icon>{{ icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content >
            <v-list-item-title>{{ text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main >
      <router-view ></router-view>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: null,
      links: [
        ['mdi-file-find-outline', 'Tra Cứu','/'],
        ['mdi-send', 'Send','/about'],
      ],
    }),
  }
</script>