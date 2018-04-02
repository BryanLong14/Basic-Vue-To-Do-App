<template>
  <div id="app">
    <ul>
      <li v-for="(tasker, index) in taskListing" v-bind:key="tasker.task">
        <p v-bind:class="{doneTask : tasker.done}">{{tasker.task}}</p>
        <input v-model="tasker.done" type="checkbox" />
        <button v-on:click="deleteItem(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      taskListing: [
        {
          done: false,
          task: "Build Vue App with To-Do List"
        },
        {
          done: false,
          task: "Create Components"
        },
        {
          done: false,
          task: "Add in async"
        }
      ]
    };
  },
  methods: {
    deleteItem(index) {
      this.taskListing.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul {
  list-style: none;
  margin-right: 20px;
}

li {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.doneTask {
  text-decoration: line-through;
}
</style>
