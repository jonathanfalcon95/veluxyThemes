<template>
  <div>
    <login-form />
  </div>
</template>

<script>
import brand from '~/static/text/brand'
import LoginForm from '~/components/Forms/Login'

export default {
  components: {
    LoginForm
  },
  head() {
    return {
      title: brand.hosting.name + ' - Login'
    }
  }
}
</script>
