<template>
  <theme-wrapper theme="passion">
    <login-form />
  </theme-wrapper>
</template>

<script>
import brand from '~/static/text/brand'
import LoginForm from '~/components/movie/Forms/Login'
import ThemeWrapper from '~/components/ThemeWrapper'

export default {
  components: {
    LoginForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.movie.name + ' - Login'
    }
  }
}
</script>
