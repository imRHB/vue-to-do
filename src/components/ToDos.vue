<template>
  <div class="container">
    <h1 class="fw-bold text-center">Simple To-Do</h1>
    <div class="d-flex">
      <input
        v-model="task"
        type="text"
        placeholder="Enter to-do"
        class="form-control"
      />
      <button class="btn btn-primary" @click="addTask">ADD</button>
    </div>

    <div class="row my-5 g-4">
      <div
        v-for="(task, idx) in tasks"
        :key="idx"
        class="col-12 col-md-3 col-xl-3"
      >
        <div class="card text-bg-light mb-3" style="max-width: 18rem">
          <div
            class="card-header"
            @click="deleteTask(idx)"
            style="cursor: pointer"
          >
            Delete
          </div>
          <div class="card-body">
            <h5 class="card-title">{{ task.title.slice(0, 12) }}</h5>
            <p class="card-text">
              {{ task.title }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import todos from "../assets/todos.json";

export default {
  data() {
    return {
      task: "",
      tasks: [
        {
          title:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quasi, sint.",
        },
        {
          title:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas, architecto!",
        },
        {
          title:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Asperiores, nemo.",
        },
      ],
    };
  },

  methods: {
    addTask() {
      if (this.task.length === 0) return;

      this.tasks.push({
        title: this.task,
      });
      this.task = "";
    },
    deleteTask(idx) {
      this.tasks.splice(idx, 1);
    },
  },
};
</script>

<style scoped>
</style>