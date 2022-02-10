<template>
  <div>{{age}}</div>
</template>

<script lang="ts">
import { reactive, toRefs, defineComponent } from "vue";
export default defineComponent({
  setup() {
    const state = reactive({
      products: [
        {
          name: "food",
          price: "3.12",
        },
        {
          name: "szama",
          price: "3.11",
        },
        {
          name: "części samochodowe",
          price: "4.12",
        },
        {
          name: "silnik e43",
          price: "21.22",
        },
      ],
      age: 35 as string | number,
    });

    return {
      ...toRefs(state),
    };
  },
});
</script>
