<template>
  <div>
    <gradient-deco />
    <theme-wrapper theme="money">
      <contact />
    </theme-wrapper>
  </div>
</template>

<script>
import GradientDeco from '~/components/crypto/GradientDeco'
import Contact from '~/components/crypto/Forms/Contact'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    Contact,
    GradientDeco,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.crypto.name + ' - Contact'
    }
  }
}
</script>
