<template>
  <div
    v-scroll="handleScroll"
    :class="{ show: show }"
    class="page-nav"
  >
    <nav class="section-nav">
      <scrollactive
        :offset="navOffset"
        active-class="active"
        tag="section"
      >
        <a
          v-for="(item, index) in menuList"
          :key="index"
          :style="{ top: 50 * (menu.length - item.id) + 'px' }"
          :href="item.url"
          class="anchor-link scrollactive-item"
          @click="setOffset(item.offset)"
        >
          <v-tooltip
            :nudge-top="18"
            class="tooltip-wrap"
            color="primarydark"
            left
          >
            <template v-slot:activator="{ on }">
              <span v-on="on">{{ $t('mobileLanding.header_'+item.name) }}</span>
            </template>
            <span class="tooltip">{{ $t('mobileLanding.header_'+item.name) }}</span>
          </v-tooltip>
        </a>
      </scrollactive>
    </nav>
    <v-tooltip
      :nudge-top="25"
      color="primarydark"
      left
    >
      <template v-slot:activator="{ on }">
        <scrollactive
          tag="div"
        >
          <v-btn
            fab
            class="fab anchor-link scrollactive-item"
            href="#home"
            v-on="on"
          >
            <v-icon dark class="icon">mdi-arrow-up</v-icon>
          </v-btn>
        </scrollactive>
      </template>
      <span class="tooltip">To Top</span>
    </v-tooltip>  
  </div>
</template>

<style scoped lang="scss">
@import './pagenav-style';
</style>

<script>
import navMenu from '../Header/menu'

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
  data: () => ({
    menu: navMenu,
    navOffset: 20,
    show: false,
    menuList: [
      createData(navMenu[0], '#' + navMenu[0]),
      createData(navMenu[1], '#' + navMenu[1]),
      createData(navMenu[2], '#' + navMenu[2]),
      createData(navMenu[3], '#' + navMenu[3], -40)
    ]
  }),
  methods: {
    handleScroll: function() {
      if (window.scrollY > 500) {
        return (this.show = true)
      }
      return (this.show = false)
    },
    setOffset: function(offset) {
      this.navOffset = offset
    }
  }
}
</script>
