<template>
  <theme-wrapper theme="cloud">
    <register-form />
  </theme-wrapper>
</template>

<script>
import RegisterForm from '~/components/hosting/Forms/Register'
import ThemeWrapper from '~/components/ThemeWrapper'
import brand from '~/static/text/brand'

export default {
  components: {
    RegisterForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.hosting.name + ' - Register'
    }
  }
}
</script>
