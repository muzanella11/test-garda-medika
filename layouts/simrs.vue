<template>
  <v-app light>
    <v-navigation-drawer
      v-model="drawer"
      app
      permanent
      color="grey lighten-3"
      mini-variant
    >
      <div class="mb-3" />

      <nuxt-link
        v-for="(item, index) in menusRight"
        :key="index"
        :to="item.url"
        flat
      >
        <v-tooltip right>
          <template #activator="{ on, attrs }">
            <v-avatar
              class="d-block text-center mx-auto mb-9"
              size="28"
              v-bind="attrs"
              v-on="on"
            >
              <v-icon>
                mdi-{{ item.icon }}
              </v-icon>
            </v-avatar>
          </template>

          <span>
            {{ item.label }}
          </span>
        </v-tooltip>
      </nuxt-link>
    </v-navigation-drawer>

    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      menusRight: [
        {
          icon: 'home',
          name: 'home',
          label: 'Home',
          url: '/'
        },
        {
          icon: 'human-queue',
          name: 'antrian',
          label: 'Antrian',
          url: '/'
        },
        {
          icon: 'cogs',
          name: 'config',
          label: 'Config',
          url: '/'
        },
        {
          icon: 'baby-carriage',
          name: 'balita',
          label: 'Balita',
          url: '/'
        }
      ],
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
