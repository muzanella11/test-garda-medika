<template>
  <v-row class="l-mockup pb-3">
    <v-col
      cols="12"
      lg="12"
    >
      <v-card>
        <v-card-title>
          Anda Masuk Sebagai
        </v-card-title>

        <v-card-text>
          {{ user.name }}
        </v-card-text>
      </v-card>
    </v-col>

    <v-col
      cols="12"
      lg="3"
    >
      <v-card>
        <v-card-title>
          Nama (Usia)
        </v-card-title>

        <v-card-text>
          {{ entries.name }}
        </v-card-text>
      </v-card>
    </v-col>

    <v-col
      cols="12"
      lg="6"
    >
      <v-row>
        <v-col
          cols="12"
          lg="6"
        >
          <v-card>
            <v-card-title>
              Tanggal Lahir
            </v-card-title>

            <v-card-text>
              {{ entries.dob }}
            </v-card-text>
          </v-card>
        </v-col>

        <v-col
          cols="12"
          lg="6"
        >
          <v-card>
            <v-card-title>
              Nomor Rekam Medis
            </v-card-title>

            <v-card-text>
              {{ entries.medicalRecordId }}
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-col>

    <v-col
      cols="12"
      lg="3"
    >
      <v-card>
        <v-card-title>
          DPJP
        </v-card-title>

        <v-card-text>
          {{ entries.doctor }}
        </v-card-text>
      </v-card>
    </v-col>

    <v-col
      cols="12"
      lg="12"
    >
      <v-row>
        <v-col
          cols="12"
          lg="6"
        >
          <v-card>
            <v-card-title>
              Keluhan Utama
            </v-card-title>

            <v-card-text>
              {{ entries.ku }}
            </v-card-text>

            <v-divider />

            <v-card-title>
              Diagnosis Primer Dan Sekunder
            </v-card-title>

            <v-card-text>
              {{ entries.dp }}
            </v-card-text>
          </v-card>
        </v-col>

        <v-col
          cols="12"
          lg="6"
        >
          <v-card>
            <v-card-title>
              <v-row>
                <v-col cols="6">
                  Tanda-Tanda Vital

                  <v-chip label>
                    H+3
                  </v-chip>
                </v-col>

                <v-col
                  cols="6"
                  class="text-right"
                >
                  <v-chip label color="info">
                    {{ entries.condition.updatedAt }}
                  </v-chip>
                </v-col>
              </v-row>
            </v-card-title>

            <v-card-text>
              <v-row>
                <v-col
                  cols="12"
                  lg="6"
                >
                  <v-card
                    :color="`${entries.condition.value.kesadaran.status === 'green' ? 'teal' : entries.condition.value.kesadaran.status === 'yellow' ? 'amber' : entries.condition.value.kesadaran.status === 'red' ? 'red' : 'info'} accent-4`"
                    class="white--text"
                  >
                    <v-card-title>
                      Kesadaran
                    </v-card-title>

                    <v-card-text
                      class="white--text"
                    >
                      <h3 class="text-h4">
                        {{ entries.condition.value.kesadaran.value }}
                      </h3>
                    </v-card-text>
                  </v-card>
                </v-col>

                <v-col
                  cols="12"
                  lg="6"
                >
                  <v-card
                    :color="`${entries.condition.value.tekananDarah.status === 'green' ? 'teal' : entries.condition.value.tekananDarah.status === 'yellow' ? 'amber' : entries.condition.value.tekananDarah.status === 'red' ? 'red' : 'info'} accent-4`"
                    class="white--text"
                  >
                    <v-card-title>
                      Tekanan Darah
                    </v-card-title>

                    <v-card-text
                      class="white--text"
                    >
                      <h3 class="text-h4">
                        {{ entries.condition.value.tekananDarah.value }}
                        <br>
                        mmHg
                      </h3>
                    </v-card-text>
                  </v-card>
                </v-col>

                <v-col
                  cols="12"
                  lg="6"
                >
                  <v-card
                    :color="`${entries.condition.value.lajuNadi.status === 'green' ? 'teal' : entries.condition.value.lajuNadi.status === 'yellow' ? 'amber' : entries.condition.value.lajuNadi.status === 'red' ? 'red' : 'info'} accent-4`"
                    class="white--text"
                  >
                    <v-card-title>
                      Laju Nadi
                    </v-card-title>

                    <v-card-text
                      class="white--text"
                    >
                      <h3 class="text-h4">
                        {{ entries.condition.value.lajuNadi.value }}
                        <br>
                        kali/menit
                      </h3>
                    </v-card-text>
                  </v-card>
                </v-col>

                <v-col
                  cols="12"
                  lg="6"
                >
                  <v-card
                    :color="`${entries.condition.value.lajuNapas.status === 'green' ? 'teal' : entries.condition.value.lajuNapas.status === 'yellow' ? 'amber' : entries.condition.value.lajuNapas.status === 'red' ? 'red' : 'info'} accent-4`"
                    class="white--text"
                  >
                    <v-card-title>
                      Laju Napas
                    </v-card-title>

                    <v-card-text
                      class="white--text"
                    >
                      <h3 class="text-h4">
                        {{ entries.condition.value.lajuNapas.value }}
                        <br>
                        kali/menit
                      </h3>
                    </v-card-text>
                  </v-card>
                </v-col>

                <v-col
                  cols="12"
                  lg="6"
                >
                  <v-card
                    :color="`${entries.condition.value.suhuTubuh.status === 'green' ? 'teal' : entries.condition.value.suhuTubuh.status === 'yellow' ? 'amber' : entries.condition.value.suhuTubuh.status === 'red' ? 'red' : 'info'} accent-4`"
                    class="white--text"
                  >
                    <v-card-title>
                      Suhu Tubuh
                    </v-card-title>

                    <v-card-text
                      class="white--text"
                    >
                      <h3 class="text-h4">
                        {{ entries.condition.value.suhuTubuh.value }}
                        <br>
                        C
                      </h3>
                    </v-card-text>
                  </v-card>
                </v-col>

                <v-col
                  cols="12"
                  lg="6"
                >
                  <v-card
                    :color="`${entries.condition.value.ews.status === 'green' ? 'teal' : entries.condition.value.ews.status === 'yellow' ? 'amber' : entries.condition.value.ews.status === 'red' ? 'red' : 'info'} accent-4`"
                    class="white--text"
                  >
                    <v-card-title>
                      Ews
                    </v-card-title>

                    <v-card-text
                      class="white--text"
                    >
                      <h3 class="text-h4">
                        {{ entries.condition.value.ews.value }}
                      </h3>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-col>

    <v-col cols="12">
      <v-card>
        <v-card-title class="pa-0 ma-0">
          <v-sheet elevation="6" width="100%">
            <v-tabs
              v-model="tab"
              width="100%"
              background-color="cyan"
              dark
              next-icon="mdi-arrow-right-bold-box-outline"
              prev-icon="mdi-arrow-left-bold-box-outline"
              show-arrows
            >
              <v-tabs-slider color="yellow" />

              <v-tab
                v-for="(itemMenuTab, indexMenuTab) in menusTab"
                :key="indexMenuTab"
              >
                {{ itemMenuTab.label }}

                <v-badge
                  v-if="itemMenuTab.notification"
                  color="red"
                  :content="itemMenuTab.notification"
                />
              </v-tab>

              <v-tab
                v-for="i in 10"
                :key="i"
              >
                Menu lainnya {{ i }}
              </v-tab>
            </v-tabs>
          </v-sheet>
        </v-card-title>

        <v-card-text class="mt-3">
          <v-tabs
            v-model="tab"
            right
            class="mockup__content-tab"
          >
            <v-tab-item>
              <v-row
                class="pa-3"
              >
                <v-col
                  cols="12"
                  lg="3"
                >
                  <v-card>
                    <v-card-title>
                      Riwayat Berobat
                    </v-card-title>

                    <v-card-text>
                      <v-timeline
                        align-top
                        dense
                      >
                        <v-timeline-item
                          v-for="(itemMedicalHistory, indexMedicalHistory) in medicalHistory"
                          :key="indexMedicalHistory"
                          color="pink"
                          small
                        >
                          <v-row class="pt-1">
                            <v-col cols="12">
                              <nuxt-link
                                to="#"
                              >
                                <strong>{{ itemMedicalHistory.date }}</strong>
                                <br>
                                <span>
                                  {{ itemMedicalHistory.value }}
                                </span>
                              </nuxt-link>
                            </v-col>
                          </v-row>
                        </v-timeline-item>
                      </v-timeline>
                    </v-card-text>
                  </v-card>
                </v-col>

                <v-col
                  cols="12"
                  lg="9"
                >
                  <v-card>
                    <v-card-text>
                      <v-tabs vertical>
                        <v-tab
                          v-for="(itemTabsKaji, indexTabsKaji) in menusTabKaji"
                          :key="indexTabsKaji"
                        >
                          {{ itemTabsKaji.label }}
                        </v-tab>

                        <v-tab-item>
                          <v-row class="pa-3">
                            <v-col cols="12">
                              <v-card>
                                <v-card-title>
                                  <v-row>
                                    <v-col
                                      cols="12"
                                      lg="6"
                                    >
                                      Pengkajian Awal Pasien Rawat Inap
                                    </v-col>

                                    <v-col
                                      cols="12"
                                      lg="6"
                                      class="text-right"
                                    >
                                      <v-btn
                                        color="primary"
                                        text
                                        fab
                                      >
                                        <v-icon>
                                          mdi-printer
                                        </v-icon>
                                      </v-btn>
                                    </v-col>
                                  </v-row>
                                </v-card-title>

                                <v-card-text>
                                  <v-row>
                                    <v-col
                                      cols="12"
                                      lg="6"
                                    >
                                      <v-radio-group v-model="entries.anamnesis.type" :disabled="disabledForm">
                                        <v-radio
                                          v-for="(itemAnamnesis, indexAnamnesis) in anamnesisType"
                                          :key="indexAnamnesis"
                                          :label="itemAnamnesis.label"
                                          :value="itemAnamnesis.value"
                                        />
                                      </v-radio-group>

                                      <v-text-field
                                        v-if="entries.anamnesis.type === 2"
                                        v-model="entries.anamnesis.value"
                                        :disabled="disabledForm"
                                        outlined
                                        dense
                                        label="alloanamnesis"
                                      />
                                    </v-col>

                                    <v-col
                                      cols="12"
                                      lg="6"
                                    >
                                      <v-row>
                                        <v-col
                                          cols="12"
                                        >
                                          <strong>Tanggal Masuk Bangsal</strong> : {{ entries.dateIn }}
                                        </v-col>

                                        <v-col
                                          cols="12"
                                        >
                                          <strong>Anamnesis oleh</strong> : {{ entries.anamnesis.createdBy }}
                                        </v-col>
                                      </v-row>
                                    </v-col>
                                  </v-row>

                                  <v-divider class="pt-3 pb-3" />

                                  <v-row>
                                    <v-col
                                      cols="12"
                                    >
                                      <v-textarea
                                        v-model="entries.ku"
                                        outlined
                                        dense
                                        label="Keluhan Utama"
                                        :disabled="disabledForm"
                                      />
                                    </v-col>

                                    <v-col
                                      cols="12"
                                    >
                                      <v-textarea
                                        v-model="entries.rps"
                                        outlined
                                        dense
                                        label="Riwayat Penyakit Sekarang"
                                        :disabled="disabledForm"
                                      />
                                    </v-col>

                                    <v-col
                                      cols="12"
                                    >
                                      <v-textarea
                                        v-model="entries.rpd"
                                        outlined
                                        dense
                                        label="Riwayat Penyakit Dahulu"
                                        :disabled="disabledForm"
                                      />
                                    </v-col>

                                    <v-col
                                      cols="12"
                                    >
                                      <v-textarea
                                        v-model="entries.rpk"
                                        outlined
                                        dense
                                        label="Riwayat Penyakit Keluarga"
                                        :disabled="disabledForm"
                                      />
                                    </v-col>

                                    <v-col
                                      cols="12"
                                    >
                                      <v-btn
                                        outlined
                                        color="secondary"
                                        class="mr-2"
                                        :disabled="disabledEdit"
                                        @click="!isEdit ? actionEdit() : actionCancel()"
                                      >
                                        {{ !isEdit ? 'Edit' : 'Batal' }}
                                      </v-btn>

                                      <v-btn
                                        color="primary"
                                        :disabled="disabledForm"
                                        @click="actionSave"
                                      >
                                        Simpan
                                      </v-btn>
                                    </v-col>
                                  </v-row>
                                </v-card-text>
                              </v-card>
                            </v-col>
                          </v-row>
                        </v-tab-item>

                        <v-tab-item
                          v-for="n in 30"
                          :key="n"
                        >
                          <v-container fluid>
                            <v-row>
                              <v-col
                                v-for="itemPhoto in 6"
                                :key="itemPhoto"
                                cols="12"
                                md="4"
                              >
                                <v-img
                                  :src="`https://picsum.photos/500/300?image=${itemPhoto * n * 5 + 10}`"
                                  :lazy-src="`https://picsum.photos/10/6?image=${itemPhoto * n * 5 + 10}`"
                                  aspect-ratio="1"
                                />
                              </v-col>
                            </v-row>
                          </v-container>
                        </v-tab-item>
                      </v-tabs>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </v-tab-item>

            <v-tab-item
              v-for="n in 30"
              :key="n"
            >
              <v-container fluid>
                <v-row>
                  <v-col
                    v-for="itemPhoto in 6"
                    :key="itemPhoto"
                    cols="12"
                    md="4"
                  >
                    <v-img
                      :src="`https://picsum.photos/500/300?image=${itemPhoto * n * 5 + 10}`"
                      :lazy-src="`https://picsum.photos/10/6?image=${itemPhoto * n * 5 + 10}`"
                      aspect-ratio="1"
                    />
                  </v-col>
                </v-row>
              </v-container>
            </v-tab-item>
          </v-tabs>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  components: {},

  layout: 'simrs',

  data () {
    return {
      isLoading: false,
      isEdit: false,
      user: {
        name: 'dr. Dany Petra, SpPD'
      },
      tab: '',
      anamnesisType: [
        {
          label: 'Autoanamnesis',
          value: 1
        },
        {
          label: 'Alloanamnesis',
          value: 2
        }
      ],
      medicalHistory: [
        {
          date: '25 Okt 2020',
          value: 'IGD-RANAP'
        },
        {
          date: '3 Okt 2020',
          value: 'RAJAL'
        },
        {
          date: '4 SEP 2020',
          value: 'RAJAL'
        },
        {
          date: '20 Jun 2020',
          value: 'IGD'
        },
        {
          date: '1 Feb 2020',
          value: 'IGD-RANAP'
        }
      ],
      menusTabKaji: [
        {
          name: 'anamnesis',
          label: 'Anamnesis',
          url: 'javascript:;'
        },
        {
          name: 'riwalergi',
          label: 'Riw. Alergi',
          url: 'javascript:;'
        },
        {
          name: 'Status Nyeri',
          label: 'Status Nyeri',
          url: 'javascript:;'
        },
        {
          name: 'Fungsional',
          label: 'Fungsional',
          url: 'javascript:;'
        },
        {
          name: 'Resiko Jatuh',
          label: 'Resiko Jatuh',
          url: 'javascript:;'
        },
        {
          name: 'Skrining Gizi',
          label: 'Skrining Gizi',
          url: 'javascript:;'
        },
        {
          name: 'Edukasi',
          label: 'Edukasi',
          url: 'javascript:;'
        },
        {
          name: 'Pem. Fisik',
          label: 'Pem. Fisik',
          url: 'javascript:;'
        },
        {
          name: 'Lab',
          label: 'Lab',
          url: 'javascript:;'
        },
        {
          name: 'Radiologi',
          label: 'Radiologi',
          url: 'javascript:;'
        },
        {
          name: 'Daf. Masalah',
          label: 'Daf. Masalah',
          url: 'javascript:;'
        },
        {
          name: 'Tatalaksana',
          label: 'Tatalaksana',
          url: 'javascript:;'
        },
        {
          name: 'Riw. Obat',
          label: 'Riw. Obat',
          url: 'javascript:;'
        }
      ],
      menusTab: [
        {
          name: 'kaji',
          label: 'Pengkajian Awal',
          notification: 0,
          url: 'javascript:;'
        },
        {
          name: 'lab',
          label: 'Lab/Radiologi',
          notification: 2,
          url: 'javascript:;'
        },
        {
          name: 'cppt',
          label: 'Cppt Ranap',
          notification: 0,
          url: 'javascript:;'
        },
        {
          name: 'informed',
          label: 'Informed Concern',
          notification: 1,
          url: 'javascript:;'
        },
        {
          name: 'skrining',
          label: 'Skrining',
          notification: 1,
          url: 'javascript:;'
        },
        {
          name: 'rekon',
          label: 'Rekonsiliasi Obat',
          notification: 0,
          url: 'javascript:;'
        },
        {
          name: 'resume',
          label: 'Resume Medis',
          notification: 0,
          url: 'javascript:;'
        }
      ],
      entries: {
        medicalRecordId: '001234567',
        dob: '30 Jan 1997',
        name: 'Ny. Mariana',
        age: 23,
        doctor: 'dr. Febri Bahari, SpPD, KGEH',
        ku: 'Muntah berdarah sejak 1 hari yang lalu',
        dp: 'Esophageal varices with bleeding (185.01)',
        rps: 'Pasien mengalami muntah berdarah sejak 1 hari yang lalu',
        rpd: 'Pasien sebelumnya pernah mengalami gejala mata kuning',
        rpk: 'Kakak pasien juga pernah mengalami kasus muntah darah',
        anamnesis: {
          type: 2,
          value: 'Tn. Rizal (Suami)',
          createdBy: 'dr. Sukma Ayu'
        },
        dateIn: 'Senin, 26 Okt 2020, 12.00 WIB',
        condition: {
          createdAt: 'Senin, 20 Jan 2020, 01.02 WIB',
          updatedAt: 'Selasa, 25 Jan 2020, 01.02 WIB',
          value: {
            kesadaran: {
              value: 'Compos Mentis',
              status: 'green'
            },
            tekananDarah: {
              value: '110/70',
              status: 'green'
            },
            lajuNadi: {
              value: '120',
              status: 'red'
            },
            lajuNapas: {
              value: '20',
              status: 'yellow'
            },
            suhuTubuh: {
              value: '37,3',
              status: 'green'
            },
            ews: {
              value: '3',
              status: 'yellow'
            }
          }
        }
      }
    }
  },

  computed: {
    disabledEdit () {
      return this.isLoading
    },

    disabledForm () {
      return this.isLoading || !this.isEdit
    }
  },

  methods: {
    actionEdit () {
      this.isEdit = true
    },

    actionCancel () {
      this.$router.push('/')
    },

    actionSave () {
      console.info('Save :)')
    }
  }
}
</script>
