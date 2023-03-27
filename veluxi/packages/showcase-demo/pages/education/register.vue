<template>
  <theme-wrapper theme="smart">
    <register-form />
  </theme-wrapper>
</template>

<script>
import brand from '~/static/text/brand'
import ThemeWrapper from '~/components/ThemeWrapper'
import RegisterForm from '~/components/education/Forms/Register'

export default {
  components: {
    RegisterForm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.education.name + ' - Register'
    }
  }
}
</script>
