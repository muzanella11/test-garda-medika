<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <v-card>
          <v-card-title>
            Popup
          </v-card-title>

          <v-card-text>
            <v-row>
              <v-col cols="12" sm="8" md="6">
                <v-btn text color="primary" @click="openPopUp()">
                  Pop up
                </v-btn>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <div v-if="isShownPopUp" class="pop-up">
      <div class="pop-up__header">
        <v-row>
          <v-col cols="6">
            <h3>title</h3>
          </v-col>

          <v-col cols="6" class="text-right">
            <v-btn text color="primary" @click="closePopUp()">
              X
            </v-btn>
          </v-col>
        </v-row>
      </div>

      <div class="pop-up__content">
        <p>lorem ipsum</p>
      </div>

      <div class="pop-up__footer">
        footer
      </div>
    </div>

    <div v-if="isShownPopUp" class="pop-up-overlay" @click="closePopUp()" />
  </v-container>
</template>

<script>
export default {
  components: {},

  data () {
    return {
      isShownPopUp: false
    }
  },

  methods: {
    openPopUp () {
      this.isShownPopUp = true
    },

    closePopUp () {
      this.isShownPopUp = false
    }
  }
}
</script>
