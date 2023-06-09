<template>
  <fragment>
    <v-navigation-drawer
      v-if="isMobile"
      v-model="openDrawer"
      fixed
      temporary
      class="mobile-nav"
    >
      <mobile-menu :open="openDrawer" />
    </v-navigation-drawer>
    <v-app-bar
      v-scroll="handleScroll"
      id="header"
      :class="{
        fixed: fixed,
        'open-drawer': openDrawer,
        invert: invert
      }"
      class="header"
      fixed
      app
    >
      <v-container :class="{ 'fixed-width': isDesktop }">
        <div class="header-content">
          <nav
            :class="{ invert: invert }"
            class="nav-logo nav-menu"
          >
            <v-btn
              v-if="isMobile"
              :class="{ 'is-active': openDrawer }"
              class="hamburger hamburger--spin mobile-menu"
              text
              icon
              @click.stop="handleToggleOpen"
            >
              <span class="hamburger-box">
                <span class="bar hamburger-inner" />
              </span>
            </v-btn>
            <div class="logo">
              <nuxt-link
                v-if="invert"
                :to="link.movie.home"
              >
                <img
                  :src="logo"
                  alt="logo"
                >
              </nuxt-link>
              <scrollactive
                v-if="!invert && loaded"
                tag="span"
              >
                <a
                  href="#home"
                  class="anchor-link scrollactive-item"
                >
                  <img
                    :src="logo"
                    alt="logo"
                  >
                </a>
              </scrollactive>
            </div>
            <div v-if="isDesktop">
              <scrollactive
                v-if="loaded"
                :offset="navOffset"
                active-class="active"
                tag="ul"
              >
                <li
                  v-for="(item, index) in menuList"
                  :key="index"
                >
                  <v-btn
                    v-if="!invert"
                    :href="item.url"
                    class="anchor-link scrollactive-item"
                    text
                    @click="setOffset(item.offset)"
                  >
                    {{ $t('movieLanding.header_'+item.name) }}
                  </v-btn>
                  <v-btn
                    v-if="invert"
                    :href="'/' + item.url"
                    text
                  >
                    {{ $t('movieLanding.header_'+item.name) }}
                  </v-btn>
                </li>
              </scrollactive>
            </div>
          </nav>
          <hidden point="mdDown">
            <span class="divider" />
          </hidden>
          <nav
            :class="{ invert: invert }"
            class="nav-menu nav-auth"
          >
            <hidden point="xsDown">
              <v-btn :href="link.movie.login" class="text-btn" text>
                {{ $t('movieLanding.header_login') }}
              </v-btn>
              <v-btn :href="link.movie.register" class="button">
                {{ $t('movieLanding.header_register') }}
              </v-btn>
            </hidden>
            <setting-menu :invert="invert" />
          </nav>
        </div>
      </v-container>
    </v-app-bar>
  </fragment>
</template>

<style lang="scss" scoped>
@import './header-style.scss';
</style>

<script>
import logo from '~/static/images/movie-logo.svg'
import link from '~/static/text/link'
import brand from '~/static/text/brand'
import Hidden from '../Hidden'
import navMenu from './menu'
import Settings from './Settings'
import MobileMenu from './MobileMenu'

let counter = 0
function createData(name, url, offset) {
  counter += 1
  return {
    id: counter,
    name,
    url,
    offset
  }
}

export default {
  components: {
    'setting-menu': Settings,
    Hidden,
    MobileMenu
  },
  props: {
    invert: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      logo: logo,
      link: link,
      loaded: false,
      brand: brand,
      section: 0,
      fixed: false,
      openDrawer: null,
      navOffset: 20,
      menuList: [
        createData(navMenu[0], '#' + navMenu[0], 100),
        createData(navMenu[1], '#' + navMenu[1]),
        createData(navMenu[2], '#' + navMenu[2]),
        createData(navMenu[3], '#' + navMenu[3]),
        createData(navMenu[4], '#' + navMenu[4])
      ]
    }
  },
  mounted() {
    this.loaded = true
  },
  methods: {
    handleScroll: function() {
      if (window.scrollY > 80) {
        return (this.fixed = true)
      }
      return (this.fixed = false)
    },
    setOffset: function(offset) {
      this.navOffset = offset
    },
    handleToggleOpen: function() {
      this.openDrawer = !this.openDrawer
    }
  },
  computed: {
    isMobile() {
      const mdDown = this.$store.state.breakpoints.mdDown
      return mdDown.indexOf(this.$mq) > -1
    },
    isDesktop() {
      const lgUp = this.$store.state.breakpoints.lgUp
      return lgUp.indexOf(this.$mq) > -1
    }
  }
}
</script>
