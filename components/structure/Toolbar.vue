<template>
  <v-app-bar :clipped-left="clipped" fixed app>
    <v-toolbar-title v-text="title" />
    <v-spacer />
    <nuxt-link
      v-for="locale in availableLocales"
      :key="locale.code"
      :to="switchLocalePath(locale.code)"
      class="mx-4"
    >
      {{ locale.name }}
    </nuxt-link>
  </v-app-bar>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  },
  computed: {
    availableLocales () {
      return this.$i18n.locales.filter(i => i.code !== this.$i18n.locale)
    }
  }
}
</script>
