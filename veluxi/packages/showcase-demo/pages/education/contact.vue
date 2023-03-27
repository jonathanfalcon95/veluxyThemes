<template>
  <theme-wrapper theme="smart">
    <contact />
  </theme-wrapper>
</template>

<script>
import Contact from '~/components/education/Forms/Contact'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    Contact,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.education.name + ' - Contact'
    }
  }
}
</script>
