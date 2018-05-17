<template>
    <div id="page">
        <h1>{{ welcomeMessage }}</h1>
        I am {{fullName}}
        <div>
            <br><h4>Tell me your name</h4>
            <input type="text" v-model="yourName">
        </div>
        <div>
            <h2>Hello{{ catchedName }}!</h2>
        </div>
        <todo></todo>
        <div class="centerized">Created with:</div>
        <div>
            <img id="vue-logo" src="../assets/logo.png">
        </div>
        <div>
            <p>2018</p>
        </div>
    </div>
</template>

<script>
import Todo from './Todo'

export default {
  name: 'page',
  data () {
    return {
      welcomeMessage: 'Welcome to my HOME!',
      fullName: 'John Rei B. Enriquez',
      yourName: ''
    }
  },
  components: {
    Todo
  },
  methods: {

  },
  computed: {
    // a computed getter
    catchedName: function () {
      // `this` points to the vm instance
      if (this.yourName === '') {
        return ''
      }
      return ' ' + this.yourName
    }
  },
  created: function () {
    this.$http.get('https://jsonplaceholder.typicode.com/users')
      .then(function (response) {
        console.log(response.data)
      })
  }
}

</script>

<style>
    #vue-logo {
        height: 2em;
        padding: 0em 0 0 0;
    }
    .centerized {
        vertical-align: middle;
        line-height: 50px;
    }
</style>
