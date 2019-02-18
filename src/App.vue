<template>
  <v-app>
    <v-content>
      <BuggyDialog/>
    </v-content>
  </v-app>
</template>

<script>
import BuggyDialog from './components/BuggyDialog'

export default {
  name: 'App',
  components: {
      BuggyDialog
  },
  data () {
    return {
      //
    }
  }
}
</script>
