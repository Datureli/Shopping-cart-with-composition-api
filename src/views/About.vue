<template>
  <section>
    <div class="recipeContainer">
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
     
      <div class="form-container">
        <h2>{{ state.newShoppingTitle }}</h2>
        <button @click="addTitle"></button>
         <div class="list-container">
           <h2>Ingredients</h2>
        <ul v-for="(Item, index) in state.Items" :key="index">
          <li>
            {{ Item }}
            <span style="float: right; padding-right: 10px">
              <button @click="removeItem(index)">X</button>
            </span>
          </li>
        </ul>
      </div>
      </div>
    </div>
  </section>
</template>

<script>
import { reactive, defineComponent } from "vue";
export default {
  setup() {
    const { state, addItem,addTitle, removeItem } = ItemList();
    return { state, addItem,addTitle,  removeItem };
  },
};
function ItemList() {
  let state = reactive({
    input: "",
    newShoppingTitle: "",
    Items: ["item example"],
  });
  let addTitle = () => {
  return  state.newShoppingTitle
  }

  let addItem = () => {
    state.Items.push(state.input);
    state.input = "";
  };

  let removeItem = (index) => {
    state.Items.splice(index, 1);
  };
  return { state, addItem, removeItem,addTitle };
}
</script>
<style scoped>
.recipeContainer {
display: flex;
text-align: center;
max-width: 50%;
margin: auto;
}
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
button {
  border: none;
  background: transparent;
  color: red;
  cursor: pointer;
}
ul li {
  color: black;
  width: 100%;
  padding: 5px;
  margin: auto;
  text-align: center;
  justify-content: center;
  margin-top: 5px;
}
.form-container {
  border: 2px solid black;
  text-align: center;
  margin: auto 10px;
  padding: 20px;
  width: 400px;
  height: 400px;
}
</style>
