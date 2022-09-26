<template>
    <base-header/>
    <slot></slot>
    <base-footer/>
</template>

<script>
import { defineComponent } from "vue";
import BaseHeader from './BaseHeader.vue'
import BaseFooter from './BaseFooter.vue'

export default defineComponent({
    name: "BaseLayout",
    components: {
        BaseHeader,
        BaseFooter,
    },
})
</script>