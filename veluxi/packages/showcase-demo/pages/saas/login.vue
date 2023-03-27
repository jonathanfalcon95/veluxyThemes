<template>
  <theme-wrapper theme="violeta">
    <login-form />
  </theme-wrapper>
</template>

<script>
import brand from '~/static/text/brand'
import ThemeWrapper from '~/components/ThemeWrapper'
import LoginForm from '~/components/saas/Forms/Login'

export default {
  components: {
    LoginForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.saas.name + ' - Login'
    }
  }
}
</script>
