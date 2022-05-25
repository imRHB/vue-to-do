<template>
  <div class="container">
    <h1 class="text-center fw-bold">Todo List</h1>

    <div class="my-4">
      <input
        v-model="todoTitle"
        class="form-control mt-3"
        type="text"
        placeholder="Title"
        style="max-width: 360px"
      />

      <textarea
        v-model="todoDescription"
        class="form-control mt-2"
        type="text"
        placeholder="Enter to-do"
        style="max-width: 360px"
      />

      <button class="btn btn-secondary mt-3" @click="addTodo">ADD TODO</button>
    </div>

    <hr />

    <div class="row my-3 g-4">
      <div
        v-for="(todo, idx) in todoLists"
        :key="idx"
        class="col-12 col-md-3 col-xl-3"
      >
        <div class="card text-bg-light mb-3" style="max-width: 18rem">
          <div
            class="card-header"
            @click="deleteTodo(idx)"
            style="cursor: pointer"
          >
            Delete
          </div>
          <div class="card-body">
            <h5 class="card-title">
              {{ todo.title ? todo.title : "Untitled" }}
            </h5>
            <p class="card-text">
              {{ todo.description }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todoTitle: "",
      todoDescription: "",
      todoLists: [
        {
          title: "Lorem ipsum dolor",
          description:
            "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Veritatis, harum. Recusandae delectus possimus id vitae laudantium facere, adipisci numquam veritatis?",
        },
        {
          title: "Lorem, ipsum dolor sit",
          description:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Deleniti, repellendus, nisi non consectetur accusamus ipsa adipisci minus inventore, necessitatibus odit nemo? Fugit non fuga iste dolor doloremque vel optio aliquam!",
        },
        {
          title: "Lorem, ipsum",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Iure voluptates fuga rerum quae nesciunt soluta ad!",
        },
      ],
    };
  },

  methods: {
    addTodo() {
      if (this.todoDescription.length === 0) {
        alert("Please enter todo");
        return;
      }

      this.todoLists.push({
        title: this.todoTitle,
        description: this.todoDescription,
      });

      this.todoTitle = "";
      this.todoDescription = "";
    },

    deleteTodo(idx) {
      this.todoLists.splice(idx, 1);
    },
  },
};
</script>

<style scoped>
</style>