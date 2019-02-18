<template>
  <v-app>
    <v-content>
      <h2>Demonstrates both the issue and the solution</h2>
      <BuggyDialog/>
      <h2>I guess this is the right solution?</h2>
      <PreferredDialog/>
      <h2>First attempt - This is just buggy...</h2>
      <ReallyBuggyDialog/>
    </v-content>
  </v-app>
</template>

<script>
import BuggyDialog from './components/BuggyDialog'
import PreferredDialog from './components/PreferredDialog'
import ReallyBuggyDialog from './components/ReallyBuggyDialog'

export default {
  name: 'App',
  components: {
      BuggyDialog,
      PreferredDialog,
      ReallyBuggyDialog
  }
}
</script>
