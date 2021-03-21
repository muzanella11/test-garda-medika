<template>
  <v-container>
    <v-row justify="center" align="center">
      <v-col cols="12">
        <v-card>
          <v-card-title>
            Text Search
          </v-card-title>

          <v-card-text>
            <v-row>
              <v-col
                cols="4"
              >
                <v-text-field
                  v-model="keyword"
                  placeholder="Find word"
                />
              </v-col>

              <v-col
                cols="4"
              >
                <v-btn
                  color="primary"
                  @click="findWord"
                >
                  <v-icon>
                    mdi-magnify
                  </v-icon>
                </v-btn>
              </v-col>

              <v-col
                v-if="result.length > 0"
                cols="12"
              >
                Found {{ result.length }} occurances of the word "{{ keyword }}" in the below text.
              </v-col>

              <v-col cols="12">
                <v-divider class="mb-3" />

                {{ entries }}
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
      keyword: '',
      result: [],
      entries: 'Turtles are reptiles of the order Chelonii or Testudines characterised by a special bony or cartilaginous shell developed from their ribs and acting as a shield. "Turtle" may either refer to the order as a whole, or to particular turtles which make up a form taxon that is not monophyletic. The order Chelonii or Testudines includes both extant (living) and extinct species. The earliest known turtles date from 220 million years ago, making turtles one of the oldest reptile groups and a more ancient group than lizards, snakes or crocodiles. Of the many species alive today, some are highly endangered. Like all other extant reptiles, turtles are ectotherms their internal temperature varies according to the ambient environment, commonly called cold-blooded. However, because of their high metabolic rate, leatherback sea turtles have a body temperature that is noticeably higher than that of the surrounding water. Like other amniotes (reptiles, dinosaurs, birds, and mammals), they breathe air and do not lay eggs underwater, although many species live in or around water. The largest turtles are aquatic.'
    }
  },

  methods: {
    findWord () {
      if (!this.keyword) return

      const regex = new RegExp(this.keyword, 'g')

      const result = this.entries.match(regex)

      this.result = result
    }
  }
}
</script>
