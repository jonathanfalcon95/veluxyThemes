<template>
  <theme-wrapper theme="cloud">
    <login-form />
  </theme-wrapper>
</template>

<script>
import LoginForm from '~/components/hosting/Forms/Login'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    LoginForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.hosting.name + ' - Login'
    }
  }
}
</script>
