<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <nuxt-link to="/">
        <v-toolbar-title v-text="title" />
      </nuxt-link>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Image Rotator',
          to: '/image-rotator'
        },
        {
          icon: 'mdi-apps',
          title: 'Tab Content',
          to: '/tab-content'
        },
        {
          icon: 'mdi-apps',
          title: 'Text Search',
          to: '/text-search'
        },
        {
          icon: 'mdi-apps',
          title: 'Popup',
          to: '/popup'
        },
        {
          icon: 'mdi-apps',
          title: 'Table',
          to: '/table'
        },
        {
          icon: 'mdi-apps',
          title: 'EHR Mockup',
          to: '/mockup'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Frontend Test Garda Medica'
    }
  }
}
</script>
