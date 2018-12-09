<template>
  <div >
    <!-- <form id="form-component">
      <input type="text" name="task" id="">
      <button v-on:click="pushTask">Save Task</button>
    </form> -->
    <div>
      <ul>
        <li v-for="(todo, index) in todos" v-bind:key="index">
          {{ todo.text }}
          {{ index }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script >
  export default {
    data() {
      return{
        todos: [
          { text: 'First to render' },
          { text: 'Second to render' },
          { text: 'Third to render' },
        ],
      }
    },
  };
</script>


