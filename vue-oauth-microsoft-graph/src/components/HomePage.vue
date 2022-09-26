<template>
    <div class="header">
        <h1>Here's the Home page !</h1>
        <div class="buttons">
            <base-button value="BaseButton with custom margin" />
            <base-button disabled="true" value="Basebutton disabled" />
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BaseButton from "./BaseButton.vue";

export default defineComponent({
    name: "HomePage",
  components: { BaseButton },
  props: {
  },
});
</script>

<style scoped>
    .header{
        margin: 10em;
    }
    .buttons{
        display: flex;
        padding: 0 10px;
        justify-content: space-between;
    }
</style>