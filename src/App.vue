<template>
  <div id="app">
    <button @click="test1()">Tutorialspoint.com</button>
    <button @click="test2()">Click 2</button>
    <button @click="test3()">Click 3</button>
    <button @click="test4()">Click 4</button>
    <button @click="test5()">Click 5</button>
    <button @click="test6()">Click 6</button>
    <button @click="test7()">Click 7</button>
    <button @click="test8()">Click 8</button>
    <br/><br/>
    <div style="border: 1px solid red;padding: 10px 10px">
      <router-view/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {

    }
  },
  methods: {
    test1() {
      var myThis = this
      this.$router.push({path: '/test1'});
    },
    test2() {
      var myThis = this
      this.$router.push({path: '/test2'});
    },
    test3() {
      var myThis = this
      this.$router.push({path: '/test3'});
    },
    test4() {
      var myThis = this
      setTimeout(function(){ myThis.$router.push({path: '/test4'}) }, 30000)
    },
    test5() {
      var myThis = this
      this.$router.push({path: '/test5'});
    },
    test6() {
      var myThis = this
      setTimeout(function(){ myThis.$router.push({path: '/test6'}) }, 60000)
    },
    test7() {
      var myThis = this
      this.$router.push({path: '/test7'});
    },
    test8() {
      var myThis = this
      setTimeout(function(){ myThis.$router.push({path: '/test8'}) }, 90000)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app > button {
  background-color: crimson;
  color: #FFF;
  padding: 5px 10px;
  border: 1px solid transparent;
}
</style>
