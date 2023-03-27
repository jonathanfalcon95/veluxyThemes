<template>
  <div>
    <v-navigation-drawer
      v-model="openDrawer"
      :width="600"
      absolute
      class="drawer"
      temporary
      right
    >
      <div class="opt-wrap">
        <v-app-bar class="appbar" fixed>
          <v-tabs
            v-model="tab"
            class="tabs"
            color="primary"
            centered
          >
            <hidden point="smUp">
              <v-btn icon @click="handleClose()">
                <v-icon>mdi-arrow-left</v-icon>
              </v-btn>
            </hidden>
            <v-tabs-slider color="primary" />
            <v-tab class="tab-label">
              <v-icon>mdi-palette-outline</v-icon>
              Theme
            </v-tab>
            <v-tab class="tab-label">
              <v-icon>mdi-bookmark-multiple-outline</v-icon>
              Explore
            </v-tab>
          </v-tabs>
        </v-app-bar>
        <v-tabs-items v-model="tab">
          <v-tab-item>
            <div class="theme-switched">
              <v-card class="paper">
                <v-row>
                  <v-col sm="6" cols="12" class="margin-bottom">
                    <h6 class="title">Theme Mode</h6>
                    <v-row>
                      <v-col class="py-0" align="start" justify="start">
                        <label class="overline">Light</label>
                        <v-switch
                          v-model="dark"
                          class="switch-toggle"
                          color="primary"
                          @change="changeMode()"
                        />
                        <label class="overline">Dark</label>
                      </v-col>
                    </v-row>
                  </v-col>
                  <v-col sm="6" cols="12">
                    <h6 class="title">Layout Direction</h6>
                    <v-row>
                      <v-col class="py-0 flex" align="start" justify="start">
                        <label class="overline">LTR</label>
                        <v-switch
                          v-model="rtl"
                          class="switch-toggle"
                          color="primary"
                          @change="changeDirection()"
                        />
                        <label class="overline">
                          RTL
                          <br />
                          <i class="caption">Best view in arabic</i>
                        </label>
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
              </v-card>
            </div>
            <div class="theme-color">
              <v-card class="paper">
                <h6 class="title">Color Combinations</h6>
                <v-row>
                  <v-col
                    v-for="(clr, index) in colorList"
                    :key="index"
                    sm="3"
                    cols="6"
                  >
                    <v-tooltip top>
                      <template v-slot:activator="{ on }">
                        <v-btn
                          text
                          class="swatch"
                          :class="{ active: selectedColor === clr }"
                          @click="changeColor(clr)"
                          v-on="on"
                        >
                          <span
                            class="primary-swatch"
                            :style="{
                              background: themeList[clr].primary,
                              boxShadow: '0 0 0 6px ' + themeList[clr].primarylight + ', 0 0 0 12px ' + themeList[clr].primarydark + ', rgba(0, 0, 0, 0.45) 0px 0px 6px 12px'
                            }"
                          >
                            &nbsp;
                          </span>
                          <span
                            class="secondary-swatch"
                            :style="{
                              background: themeList[clr].secondary,
                              boxShadow: '0 0 0 4px ' + themeList[clr].secondarylight + ', 0 0 0 8px ' + themeList[clr].secondarydark + ', rgba(0, 0, 0, 0.30) 0px 0px 5px 9px'
                            }"
                          >
                            &nbsp;
                          </span>
                        </v-btn>
                      </template>
                      <span>{{ clr }}</span>
                    </v-tooltip>
                  </v-col>
                </v-row>
              </v-card>
            </div>
          </v-tab-item>
          <v-tab-item>
            <div class="explore">
              <ul>
                <li>
                  <a href="/medical" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[9]" alt="medical" />
                    </figure>
                    Medical
                  </a>
                </li>
                <li>
                  <a href="/movie" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[10]" alt="movie" />
                    </figure>
                    Movie Entertainment
                  </a>
                </li>
                <li>
                  <a href="/education" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[11]" alt="education" />
                    </figure>
                    Education
                  </a>
                </li>
                <li>
                  <a href="/mobile-apps" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[6]" alt="mobile apps" />
                    </figure>
                    Mobile Apps
                  </a>
                </li>
                <li>
                  <a href="/saas" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[8]" alt="saas" />
                    </figure>
                    SaaS
                  </a>
                </li>
                <li>
                  <a href="/agency" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[1]" alt="agency" />
                    </figure>
                    Agency
                  </a>
                </li>
                <li>
                  <a href="/profile" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[7]" alt="agency" />
                    </figure>
                    Portfolio Profile
                  </a>
                </li>
                <li>
                  <a href="/cryptocurrency" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[3]" alt="crypto" />
                    </figure>
                    Cryptocurrency
                  </a>
                </li>
                <li>
                  <a href="/fashion" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[4]" alt="fashion" />
                    </figure>
                    Fashion
                  </a>
                </li>
                <li>
                  <a href="/hosting" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[5]" alt="hosting" />
                    </figure>
                    Cloud Hosting
                  </a>
                </li>
                <li>
                  <a href="/architect" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[2]" alt="architect" />
                    </figure>
                    Interior Architect
                  </a>
                </li>
                <li>
                  <a href="/femine" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[13]" alt="femine" />
                    </figure>
                    Portfolio 2
                  </a>
                </li>
                <li>
                  <a href="/unisex" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[14]" alt="unisex" />
                    </figure>
                    Portfolio 3
                  </a>
                </li>
                <li>
                  <a href="/maskulino" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[15]" alt="maskulino" />
                    </figure>
                    Portfolio 4
                  </a>
                </li>
                <li>
                  <a href="http://ilhammeidi.github.io/luxivue-doc" target="_blank">
                    <figure>
                      <img :src="imgAPI.showcase[12]" alt="documentation" />
                    </figure>
                    Documentation
                  </a>
                </li>
              </ul>
            </div>
          </v-tab-item>
        </v-tabs-items>
      </div>
    </v-navigation-drawer>
    <div class="btn" :class="{ active: openDrawer }">
      <v-btn icon @click="handleToggleOpenTheme()">
        <v-icon>mdi-palette-outline</v-icon>
      </v-btn>
      <v-btn icon @click="handleToggleOpenExplore()">
        <v-icon>mdi-bookmark-multiple-outline</v-icon>
      </v-btn>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import './palette-style.scss';
</style>

<script>
import imgAPI from '~/static/images/imgAPI'
import Hidden from '../agency/Hidden'

const colorList = [
  'joker',
  'violeta',
  'passion',
  'purple',
  'burgundy',
  'violet',
  'roseGold',
  'vampire',
  'ubuntu',
  'gold',
  'deepBlue',
  'fresh',
  'mint',
  'smart',
  'oceanBlue',
  'cloud',
  'littleQueen',
  'botani',
  'money',
  'greenLeaf',
  'greenNature',
  'brown',
  'grayscale',
  'black'
];

let darkMode = 'false'
if (typeof Storage !== 'undefined') { // eslint-disable-line
  darkMode = localStorage.getItem('luxiDarkMode') || 'false'
}

export default {
  components: {
    Hidden
  },
  data: () => ({
    tab: null,
    imgAPI: imgAPI,
    colorList: colorList,
    openDrawer: false,
    dark: darkMode === 'true',
    rtl: false
  }),
  methods: {
    changeMode() {
      localStorage.setItem('luxiDarkMode', this.dark)
      this.$vuetify.theme.dark = this.dark
    },
    changeDirection() {
      this.$vuetify.rtl = this.rtl
      document.dir = this.rtl ? 'rtl' : 'ltr'
    },
    handleToggleOpenTheme() {
      this.tab = 0
      this.openDrawer = !this.openDrawer
    },
    handleToggleOpenExplore() {
      this.tab = 1
      this.openDrawer = !this.openDrawer
    },
    handleClose() {
      this.openDrawer = false
    }
  },
  props: {
    selectedColor: {
      type: String,
      required: true
    },
    changeColor: {
      type: Function,
      required: true
    },
    themeList: {
      type: Object,
      required: true
    }
  }
}
</script>
