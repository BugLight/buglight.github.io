<template>
  <v-app dark>
    <v-app-bar
      app
      flat
      hide-on-scroll
    >
      <v-spacer />
      <h1 class="buglight-title">
        {{ title }}
      </h1>
      <v-spacer />
      <template v-slot:extension>
        <v-tabs centered>
          <v-tab
            nuxt
            v-for="link in links"
            :key="link.text"
            :to="link.to"
          >
            {{ link.text }}
          </v-tab>
        </v-tabs>
      </template>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer app>
      <span>&copy; Daniil Zhukov {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      title: 'Buglight',
      links: [
        {
          text: 'About',
          to: '/',
        },
        {
          text: 'Blog',
          to: '/blog',
        }
      ]
    }
  }
}
</script>

<style>
.buglight-title {
  font-family: 'Chakra Petch', sans-serif;
  text-transform: uppercase;
}
</style>
