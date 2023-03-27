<template>
  <theme-wrapper theme="cloud">
    <contact />
  </theme-wrapper>
</template>

<script>
import Contact from '~/components/hosting/Forms/Contact'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    Contact,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.hosting.name + ' - Contact'
    }
  }
}
</script>
