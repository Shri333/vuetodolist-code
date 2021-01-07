<template>
  <div>
    <nav class="navbar navbar-light bg-success bg-gradient">
      <span class="navbar-brand mx-auto text-light fs-3 fw-bold"
        >Vue Todo List</span
      >
    </nav>
    <div class="w-80 container mt-4">
      <div class="input-group input-group-lg mb-3">
        <input
          type="text"
          class="form-control"
          placeholder="Enter Task"
          v-model="task"
          @keyup.enter="addItem"
        />
        <button type="button" class="btn btn-success" @click="addItem">
          Add
        </button>
      </div>
      <hr />
      <div v-for="(item, index) in list" :key="item">
        <Item :task="item" @deltask="deleteItem(index)"></Item>
      </div>
    </div>
  </div>
</template>

<script>
import Item from "./components/Item";

export default {
  name: "App",
  components: {
    Item
  },
  data() {
    return {
      list: [],
      task: ""
    };
  },
  methods: {
    addItem() {
      this.list.push(this.task);
      this.task = "";
    },
    deleteItem(index) {
      this.list.splice(index, 1);
    }
  }
};
</script>
