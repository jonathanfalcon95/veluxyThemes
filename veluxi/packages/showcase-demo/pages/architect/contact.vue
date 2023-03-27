<template>
  <theme-wrapper theme="greenLeaf">
    <div class="main-wrap">
      <contact-frm />
    </div>
  </theme-wrapper>
</template>

<style lang="scss" scoped>
.main-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
  @include use-theme(
    background,
    $light-background-paper,
    $dark-background-default
  );
}
</style>

<script>
import brand from '~/static/text/brand'
import ThemeWrapper from '~/components/ThemeWrapper'
import ContactFrm from '~/components/architect/Forms/Contact'

export default {
  components: {
    ContactFrm,
    ThemeWrapper
  },
  head() {
    return {
      title: brand.architect.name + ' - Contact'
    }
  }
}
</script>
