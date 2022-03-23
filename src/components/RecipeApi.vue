<template>
  <Suspense>

  </Suspense>
</template>

<script>
import { ref } from "vue";
export default {
  async setup() {
    const result = await axios.get("url");

    return {
      result,
    };
  },
};
</script>
