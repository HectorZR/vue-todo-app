<template>
  <div class="container">
    <div id="form-component">
      <input type="text" name="task" id="" v-model="task">
      <button v-on:click="pushTask">Save Task</button>
    </div>
    <div class="list-container">
      <ul class="list" >
        <li v-for="(todo, index) in todos" v-bind:key="index">
          {{ todo.text }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script >
export default {
  data() {
    return {
      todos: [],
      task: '',
    };
  },
  methods: {
    pushTask() {
      this.todos.push({ text: this.task });
      this.task = '';
    },
  },
};
</script>

<style lang="scss" scoped>
// .container{
//   display: flex;
//   align-content: center;
//   flex-direction: center;
// }
.list-container {
  width: 50%;
  background-color: green;
  color: white;

  .list {
    background-color: blue;
    width: 50%;
    list-style-type: none;
  }
}
</style>
