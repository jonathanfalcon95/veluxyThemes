<template>
  <theme-wrapper theme="passion">
    <register-form />
  </theme-wrapper>
</template>

<script>
import brand from '~/static/text/brand'
import RegisterForm from '~/components/movie/Forms/Register'
import ThemeWrapper from '~/components/ThemeWrapper'

export default {
  components: {
    RegisterForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.movie.name + ' - Register'
    }
  }
}
</script>
