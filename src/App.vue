<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>MIDES</span>
      </v-toolbar-title>
    </v-toolbar>

    <v-content>
      <MideList/>
    </v-content>
  </v-app>
</template>

<script>
import MideList from './components/MideList'

export default {
  name: 'App',
  components: {
    MideList
  },
  data () {
    return {
      //
    }
  }
}
</script>
