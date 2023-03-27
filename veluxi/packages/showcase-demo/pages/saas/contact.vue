<template>
  <theme-wrapper theme="violeta">
    <contact />
  </theme-wrapper>
</template>

<script>
import brand from '~/static/text/brand'
import ThemeWrapper from '~/components/ThemeWrapper'
import Contact from '~/components/saas/Forms/Contact'

export default {
  components: {
    ThemeWrapper,
    Contact
  },
  head() {
    return {
      title: brand.saas.name + ' - Contact'
    }
  }
}
</script>
