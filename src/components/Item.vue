<template>
  <div class="input-group input-group-lg mb-3">
    <input type="text" class="form-control" :value="task" />
    <button type="button" class="btn btn-danger" @click="deleteItem">
      Delete
    </button>
  </div>
</template>

<script>
export default {
  name: "Item",
  props: {
    task: String
  },
  methods: {
    deleteItem() {
      this.$emit("deltask");
    }
  }
};
</script>
