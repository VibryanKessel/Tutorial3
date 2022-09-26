<template>
    <div class="header">
        <h1>Here's the Home page !</h1>
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomePage",
  props: {
  },
});
</script>

<style scoped>
    .header{
        margin: 10em;
    }
</style>