<template>
  <theme-wrapper theme="joker">
    <contact />
  </theme-wrapper>
</template>

<script>
import brand from '~/static/text/brand'
import ThemeWrapper from '~/components/ThemeWrapper'
import Contact from '~/components/mobile/Forms/Contact'

export default {
  components: {
    Contact,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.mobile.name + ' - Contact'
    }
  }
}
</script>
