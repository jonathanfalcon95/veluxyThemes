<template>
  <div>
    <gradient-deco />
    <theme-wrapper theme="money">
      <register-form />
    </theme-wrapper>
  </div>
</template>

<script>
import GradientDeco from '~/components/crypto/GradientDeco'
import brand from '~/static/text/brand'
import ThemeWrapper from '~/components/ThemeWrapper'
import RegisterForm from '~/components/crypto/Forms/Register'

export default {
  components: {
    GradientDeco,
    RegisterForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.crypto.name + ' - Register'
    }
  }
}
</script>
