<template>
  <div>
    <TLbar></TLbar>
    <TLheader></TLheader>
    <TLlist></TLlist>
  </div>
</template>

<script>
import TLheader from "./TLheader";
import TLlist from "./TLlist";
import TLbar from "./TLbar";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    TLheader,
    TLlist,
    TLbar
  }
};
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
</style>
