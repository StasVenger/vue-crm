<template>
  <component :is="layout + '-layout'" v-if="layout">
    <router-view/>
  </component>
</template>

<script>
import AuthLayout from '@/layouts/AuthLayout';
import MainLayout from '@/layouts/MainLayout';
export default {
  computed: {
    layout() {
      return (this.$route.meta.layout || 'empty')
    }
  },
  components: {AuthLayout, MainLayout}
}
</script>

<style lang="scss">
@import '~materialize-css/dist/css/materialize.min.css';
@import 'assets/index.css';
</style>