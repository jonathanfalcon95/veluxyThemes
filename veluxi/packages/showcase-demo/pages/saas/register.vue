<template>
  <theme-wrapper theme="violeta">
    <register-form />
  </theme-wrapper>
</template>

<script>
import brand from '~/static/text/brand'
import RegisterForm from '~/components/saas/Forms/Register'
import ThemeWrapper from '~/components/ThemeWrapper'

export default {
  components: {
    RegisterForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.saas.name + ' - Register'
    }
  }
}
</script>
