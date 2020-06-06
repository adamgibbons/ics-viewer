<template>
  <div id="app">
    <div class='row'>
      <div class='col'>
        <h3>Input</h3>
        <p>form goes here</p>
        <pre>{{vEvent}}</pre>
      </div>
      <div class='col'>
        <h3>Output (vEvent)</h3>
        <vEventOut v-bind:vEvent="this.vEvent" />
      </div>
    </div>
  </div>
</template>

<script>
import vEventOut from './components/vEventOut.vue'

export default {
  name: 'App',
  components: {
    vEventOut
  },
  data() {
    return {
      vEvent: {
        start: [2018, 5, 30, 6, 30],
        duration: { hours: 6, minutes: 30 },
        title: 'Bolder Boulder',
        description: 'Annual 10-kilometer run in Boulder, Colorado',
        location: 'Folsom Field, University of Colorado (finish line)',
        url: 'http://www.bolderboulder.com/',
        geo: { lat: 40.0095, lon: 105.2669 },
        categories: ['10k races', 'Memorial Day Weekend', 'Boulder CO'],
        status: 'CONFIRMED',
        busyStatus: 'BUSY',
        organizer: { name: 'Admin', email: 'Race@BolderBOULDER.com' },
        attendees: [
          { name: 'Adam Gibbons', email: 'adam@example.com', rsvp: true, partstat: 'ACCEPTED', role: 'REQ-PARTICIPANT' },
          { name: 'Brittany Seaton', email: 'brittany@example2.org', dir: 'https://linkedin.com/in/brittanyseaton', role: 'OPT-PARTICIPANT' }
        ]
      }
    }
  }
}
</script>

<style>
body, html {
  padding: 0;
  margin: 0;
  /*display: flex;*/
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0;
  padding: 0;
  height: 100%;
  background: #888;
}
.row {
  display: flex;
  flex-flow: row nowrap;
  margin: 0;
  padding: 0;
}
.col {
  /*flex: 1 1 auto;*/
  background: #ddd;
  margin: .1em;
  padding: 1em;
}
</style>
