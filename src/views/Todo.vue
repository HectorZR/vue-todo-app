<template>
  <div class="container">
    <div id="form-component">
      <input type="text" name="task" v-model.trim="task" placeholder="Register your to-do task">
      <button v-on:click="pushTask">Save Task</button>
    </div>
    <div v-if="showAlert" class="alert">
      <p>{{ alert }}</p>
    </div>
    <div class="list-container">
      <ul class="list" >
        <li class="item" v-for="(todo, index) in todos" v-bind:key="index">
          {{ todo.text }} <button class="task-delete-button" on:click="deleteTask(index)">X</button>
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
* {
  padding: 0px;
  margin: 0px;
}
.container{
  display: flex;
  flex-direction: column;
  align-items: center;

  #form-component{
    margin-bottom: 20px;
  }

  .list-container {
    width: 50vw;
    height: 500px;
    margin-top: 20px;
    background-color: green;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;

    .list {
      background-color: gray;
      width: 25vw;
      list-style-type: none;

      .item {
        display: flex;
        align-items: flex-end;

        .task-delete-button {
          margin-right: 0px;
        }
      }
    }
  }

  .alert {
    background-color: yellow;
    height: 40px;
    width: 20vw;
    min-width: 250px;
  }
}
</style>
