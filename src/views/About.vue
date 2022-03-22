<template>
  <section>
    <div style="display: flex">
      <div class="form-container" style="border: 2px solid black">
        <form @submit.prevent="addItem">
          <div>
            <label>List Title</label>
            <input type="text" v-model="state.newShoppingTitle" />
          </div>

          <div>
            <label>Product Name</label>
            <input v-model="state.input" type="text" />
          </div>
          <div>
            <button type="submit" class="submit">Add product</button>
          </div>
        </form>
      </div>
      <div class="list-container">
        <ul v-for="(Item, index) in state.Items" :key="index">
          <li>
            {{ Item }}
            <span style="float: right; padding-right: 10px">
              <button @click="removeItem(index)">X</button>
            </span>
          </li>
        </ul>
      </div>
      <div>
        <h2>List title: {{ state.newShoppingTitle }}</h2>
      </div>
    </div>
  </section>
</template>

<script>
import { reactive, defineComponent } from "vue";
export default {
  setup() {
    const { state, addItem, removeItem } = ItemList();
    return { state, addItem, removeItem };
  },
};
function ItemList() {
  let state = reactive({
    input: "",
    newShoppingTitle: "",
    Items: ["item example"],
  });
  let addItem = () => {
    state.Items.push(state.input);
    state.input = "";
  };

  let removeItem = (index) => {
    state.Items.splice(index, 1);
  };
  return { state, addItem, removeItem };
}
</script>
<style scoped>
input {
  width: 150px;
  height: 30px;
  margin: 5px 35px;
  border: 2px solid #008000;
}
h2,
label {
  color: #000000;
}
.submit {
  margin: 10px;
  padding: 10px;
  border-radius: 0px;
  border: 0px;
  background: green;
  color: white;
}
ul li {
  color: black;
  list-style: none;
  border: 2px solid green;
  width: 30%;
  padding: 5px;
  margin: auto;
  text-align: center;
  justify-content: center;
  margin-top: 10px;
}
.form-container {
  text-align: center;
  margin: auto;
  width: 50%;
  height: 400px;
}
</style>
