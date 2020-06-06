<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1> -->
    <!-- <pre>{{vEvent}}</pre> -->
    <div v-for='(line, index) in output' :key='index'>
      <div class='line'>{{line}}</div>
    </div>
  </div>
</template>

<script>
const ics = require('ics')

export default {
  name: 'HelloWorld',
  props: {
    vEvent: Object
  },
  computed: {
    output() {
      return ics.createEvent(this.vEvent, (e, v) => {
        return v.split('\r\n')
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.line {
  /*border: 1px solid red;*/
  background: #eee;
  margin: 4px 0;
  line-height: 2;
}
</style>
