<template>
  <div class="container">
    <div id="form-component">
      <input type="text" name="task" v-model.trim="task" placeholder="Register your to-do task">
      <button v-on:click="pushTask">Save Task</button>
    </div>
    <div v-if="showAlert">
      <p>{{ alert }}</p>
    </div>
    <div class="list-container">
      <ul class="list" >
        <li v-for="(todo, index) in todos" v-bind:key="index">
          {{ todo.text }} <button v-on:click="deleteTask(index)">X</button>
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
      alert: '',
      showAlert: false,
    };
  },
  methods: {
    pushTask() {
      this.showAlert = false;

      if (this.task !== '') {
        this.todos.push({
          text: this.task,
        });

        this.task = '';
      } else {
        this.alert = 'Type a task';

        this.showAlert = true;
      }
    },
    deleteTask(id) {
      this.todos.splice(id, 1);
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
    background-color: gray;
    width: 50%;
    list-style-type: none;
  }
}
</style>
