/* eslint no-undef: 0 */
/* eslint-disable no-alert, no-console */

<template>
  <div id="maintodo">
    <div>Write down what you want done</div>
    <input type='text' v-on:keyup.enter="addTask" v-model='newTask'>
    <ul id="tasklist">
        <li v-for="task in tasks" :key="task">
            {{ task }}
        </li>
    </ul>
  </div>

</template>

<script>
export default {
  name: 'todo',
  data () {
    return {
      newTask: '',
      tasks: []
    }
  },
  methods: {
    addTask: function (e) {
      this.tasks.push(this.newTask)
    }
  }
}
</script>

<style scoped>

h2 {
  font: 400 40px/1.5 Helvetica, Verdana, sans-serif;
  margin: 0;
  padding: 0;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

li {
  font: 200 20px/1.5 Helvetica, Verdana, sans-serif;
  border-bottom: 1px solid #ccc;
}

li:last-child {
  border: none;
}

li a {
  text-decoration: none;
  color: #000;
  display: block;
  width: 200px;

  -webkit-transition: font-size 0.3s ease, background-color 0.3s ease;
  -moz-transition: font-size 0.3s ease, background-color 0.3s ease;
  -o-transition: font-size 0.3s ease, background-color 0.3s ease;
  -ms-transition: font-size 0.3s ease, background-color 0.3s ease;
  transition: font-size 0.3s ease, background-color 0.3s ease;
}

li a:hover {
  font-size: 30px;
  background: #f6f6f6;
}
</style>
/* eslint-enable no-alert */
