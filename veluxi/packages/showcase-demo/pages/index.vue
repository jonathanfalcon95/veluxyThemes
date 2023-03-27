<template>
  <div class="main-wrap">
    <banner />
    <div id="explore">
      <explore />
    </div>
    <footer-main />
  </div>
</template>

<style scoped lang="scss">
@import '~/assets/styles';

.main-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
  background: $light-background-paper;
}
</style>

<script>
import Banner from '../components/showcase/Banner'
import Explore from '../components/showcase/Explore'
import Footer from '../components/showcase/Footer'

export default {
  head() {
    return {
      title: 'Veluxi - Vue Single Landing Page Template Collection'
    }
  },
  components: {
    Banner,
    Explore,
    'footer-main': Footer
  }
}
</script>
