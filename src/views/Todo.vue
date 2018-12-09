<template>
  <div class="container">
    <form id="form-component">
      <input type="text" name="task" id="">
      <button v-on:click="pushTask">Save Task</button>
    </form>
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
      todos: [
        { text: 'first to render' },
      ],
    };
  },
  methods: {},
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
