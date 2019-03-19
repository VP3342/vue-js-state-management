<template>
  <div>
    <h3>Vuex State Management demo using .... Todos</h3>
    <div class="add">
      <form @submit="onSubmit">
        <input type="text" v-model="title" placeholder="Add Todo...">
        <input type="submit" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 10px;
  border: 1px solid #feda6a;
  outline: 0;
  text-transform: uppercase;
  font-family: cursive;
  font-weight: 900;
}

input[type="submit"] {
  flex: 2;
  background: #feda6a;
  border: 1px #feda6a solid;
  text-transform: uppercase;
  font-family: cursive;
  cursor: pointer;
  font-weight: 900;
}

::placeholder { /* Chrome, Firefox, Opera, Safari 10.1+ */
  color:#1d1e22;
  opacity: 1; /* Firefox */
}

:-ms-input-placeholder { /* Internet Explorer 10-11 */
  color: #1d1e22;
}

::-ms-input-placeholder { /* Microsoft Edge */
  color: #1d1e22;
}
</style>
