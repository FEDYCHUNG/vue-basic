<template>
  <div class="hello">
    <h1>Todo App</h1>
    <input
      @keyup.enter="add"
      type="text"
      v-model="title"
      placeholder="What you want to do?"
    />
    <button @click="add">Add to list</button>

    <ul>
      <li v-for="(todo, index) in todos" :key="todo.id">
        {{ todo }}
        <span @click="remove(index)" class="remove">x</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "todo",
  props: {
    msg: String
  },
  data() {
    return {
      title: "",
      todos: ["Go To Shop"]
    };
  },
  methods: {
    add() {
      if (this.title != "") {
        this.todos.unshift(this.title); // Add item from top
        // this.todos.push(this.title);
        this.title = "";
      }
    },
    remove(id) {
      // console.log(id);
      // this.todos.splice(id, 1);
      this.$delete(this.todos, id);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.remove {
  padding: 0.3rem 0.6rem;
  background-color: red;
  color: #fff;
  border-radius: 30px;
}

.remove:hover {
  cursor: pointer;
}

ul li {
  padding: 0.4rem;
}
</style>
