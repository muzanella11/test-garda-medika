<template>
  <v-container>
    <v-row justify="center" align="center">
      <v-col cols="12">
        <v-card>
          <v-card-title>
            Image Rotator
          </v-card-title>

          <v-card-text>
            <v-row justify="center" align="center">
              <v-col cols="12" sm="8" md="6">
                <a class="image-rotator" href="javascript:;">
                  <img src="http://frontend.kerjajarakjauh.id/img/kat_1.jpg">
                </a>
              </v-col>
            </v-row>
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
      entries: [
        {
          url: 'http://frontend.kerjajarakjauh.id/img/kat_1.jpg'
        }
      ]
    }
  }
}
</script>
