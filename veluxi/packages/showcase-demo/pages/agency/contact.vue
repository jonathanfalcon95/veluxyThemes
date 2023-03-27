<template>
  <theme-wrapper theme="oceanBlue">
    <decoration />
    <contact />
  </theme-wrapper>
</template>

<script>
import Contact from '~/components/agency/Forms/Contact'
import Decoration from '~/components/agency/Forms/Decoration'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    Contact,
    Decoration,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.agency.name + ' - Contact'
    }
  }
}
</script>
