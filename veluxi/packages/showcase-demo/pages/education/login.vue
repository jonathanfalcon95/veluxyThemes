<template>
  <theme-wrapper theme="smart">
    <login-form />
  </theme-wrapper>
</template>

<script>
import brand from '~/static/text/brand'
import ThemeWrapper from '~/components/ThemeWrapper'
import LoginForm from '~/components/education/Forms/Login'

export default {
  components: {
    LoginForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.education.name + ' - Login'
    }
  }
}
</script>
