<template>
  <theme-wrapper theme="fresh">
    <div class="main-wrap">
      <decoration />
      <contact />
    </div>
  </theme-wrapper>
</template>

<style scoped lang="scss">
.main-wrap {
  position: relative;
  .theme--dark & {
    background-color: $dark-background-default;
  }
  .theme--light & {
    background-color: $light-background-paper;
  }
}
</style>

<script>
import Contact from '~/components/medical/Forms/Contact'
import Decoration from '~/components/medical/Forms/Decoration'
import ThemeWrapper from '~/components/ThemeWrapper'  
import brand from '~/static/text/brand'

export default {
  components: {
    Contact,
    Decoration,
    ThemeWrapper,
  },
  head() {
    return {
      title: brand.medical.name + ' - Contact'
    }
  }
}
</script>
