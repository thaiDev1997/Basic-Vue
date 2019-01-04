<template>
  <div class="test1">
        <h3>Test1</h3>
        Full name: <input type="text" v-model="fullname"/>
        <p :class="{active: isActive, info: isValid}">First Name : {{firstname}}</p>
        <p :class="['active', 'info', isValid ? 'border' : '']">Last Name : {{lastname}}</p>
        <br/>
        First name: <input type="text" v-model="firstname"/>
        <br/>
        <new-component :class="['active']"></new-component>
        <p :style="styleObj">{{fullname}}</p>
  </div>
</template>

<script>
var newComponent = {
  template: '<div class="new-component"><h3>New Component</h3></div>'
}
export default {
  name: 'Test1',
  components: {
    'new-component' : newComponent
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      firstname: 'van',
      lastname: 'thai',
      isActive: true,
      isValid: true,
      styleObj: {
        color: 'pink',
        fontSize: '30px'
      }
    }
  },
  computed: {
    fullname: {
      get() {
        return this.firstname + ' ' + this.lastname
      },
      set(fullname) {
        let fullName = fullname.split(' ')
        this.firstname = fullName[0]
        this.lastname = fullName[1]
      }
    }
  },
  watch: {
    firstname(newFirstName) {
      this.lastname += '-'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
.active {
  color: dodgerblue;
}
p {
  width: auto;
}
.info {
  border-bottom: 1px solid cyan;
}
.border {
  border: 1px solid red;
}
</style>
