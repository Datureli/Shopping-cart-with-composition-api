<template>
    <div>

    </div>
</template>

<script>
import {ref} from 'vue'
export default {
    setup() {
        const result = ref(null)

        fetch('url')
        .then(response)
    },
}
</script>