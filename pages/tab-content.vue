<template>
  <v-container>
    <v-row justify="center" align="center">
      <v-col cols="12">
        <v-card>
          <v-card-title>
            Tab Content
          </v-card-title>

          <v-card-text>
            <div class="c-tab-content">
              <ul class="tab-content__list-menu">
                <li
                  v-for="(itemMenu, indexMenu) in entries"
                  :key="indexMenu"
                >
                  <a
                    href="javascript:;"
                    :class="[
                      itemMenu.name === tabActive ? 'active' : ''
                    ]"
                    @click="setTabActive(itemMenu.name)"
                  >
                    {{ itemMenu.name }}
                  </a>
                </li>
              </ul>

              <div class="tab-content__main-content">
                <template
                  v-for="(item, index) in entries"
                >
                  <p
                    v-if="item.name === tabActive"
                    :key="index"
                  >
                    {{ item.content }}
                  </p>
                </template>
              </div>
            </div>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  components: {},

  data () {
    return {
      tabActive: 'Tab 1',
      entries: [
        {
          name: 'Tab 1',
          content: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged"
        },
        {
          name: 'Tab 2',
          content: "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English"
        },
        {
          name: 'Tab 3',
          content: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old'
        }
      ]
    }
  },

  methods: {
    setTabActive (name) {
      this.tabActive = name
    }
  }
}
</script>
