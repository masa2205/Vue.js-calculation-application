<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <hr>
    <div>Value: <input type="number" v-model="val"></div>
    <div style="height:10px;"></div>
    <table>
      <tr><th>add:</th><td>{{ add }}</td></tr>
      <tr><th>sub:</th><td>{{ sub }}</td></tr>
      <tr><th>multiple:</th><td>{{ mult }}</td></tr>
      <tr><th>divide:</th><td>{{ div }}</td></tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'Helloworld',
  props:{
    title: String,
  },

  data:function() {
    return {
      message: '値監視',
      val: 0,
      add: 0,
      sub: 0,
      mult: 0,
      div: 0,
    };
  },
  watch: {
    val: function(value) {
      this.val = value;
      var val = parseInt(value);
      this.add = Math.floor(val + 2);
      this.sub = Math.floor(val - 2);
      this.mult = Math.floor(val * 2);
      this.div = Math.floor(val / 2);
    }
  },
  created: function(){
    this.val =5;
  }
}
</script>