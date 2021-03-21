<template>
  <v-container>
    <v-row justify="center" align="center">
      <v-col cols="12">
        <v-card>
          <v-card-title>
            Table
          </v-card-title>

          <v-card-text>
            <v-row>
              <v-col cols="12">
                <div class="v-data-table theme--light">
                  <div class="v-data-table__wrapper">
                    <table>
                      <thead>
                        <tr>
                          <th>
                            Nrm
                          </th>

                          <th>
                            Nama
                          </th>

                          <th>
                            Poli
                          </th>
                        </tr>
                      </thead>

                      <tbody>
                        <tr
                          v-for="(item, index) in entries"
                          :key="index"
                        >
                          <td>
                            {{ item.nrm }}
                          </td>
                          <td>
                            {{ item.name }}
                          </td>
                          <td>
                            {{ item.poli }}
                          </td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
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
          name: 'Sobri',
          nrm: 123,
          poli: 'Bedah Umum'
        }
      ]
    }
  },

  methods: {
    //
  }
}
</script>
