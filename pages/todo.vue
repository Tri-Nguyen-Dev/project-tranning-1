<template>
  <div class="wapper">
    <div class="todo">
      <h1 class="text-center">Todos</h1>
      <b-form-group>
        <b-form-input
          type="text"
          placeholder="Enter todo"
          required
          v-model="todo"
        ></b-form-input>
        <b-button variant="primary" class="mt-2" @click="addTodo"
          >Add todo</b-button
        >
      </b-form-group>

      <ul class="todo-list">
        <li
          class="todo-item"
          v-for="(todoItem, index) in listTodo"
          :key="index"
        >
          {{ todoItem }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Todo",
  data() {
    return {
      todo: "",
      listTodo: [],
    };
  },
  methods: {
    addTodo() {
      this.listTodo.push(this.todo);
      this.todo = "";
    },
  },
});
</script>
<style>
.wapper {
  padding-top: 56px;
}

.todo {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 5px 10px;
  max-width: 624px;
  margin: 0 auto;
  padding: 46px 12px;
}
</style>
