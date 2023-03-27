<template>
  <div>
    <gradient-deco />
    <theme-wrapper theme="money">
      <login-form />
    </theme-wrapper>
  </div>
</template>

<script>
import GradientDeco from '~/components/crypto/GradientDeco'
import brand from '~/static/text/brand'
import ThemeWrapper from '~/components/ThemeWrapper'
import LoginForm from '~/components/crypto/Forms/Login'

export default {
  components: {
    GradientDeco,
    LoginForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.crypto.name + ' - Login'
    }
  }
}
</script>
