<template>
  <base-button
    :value = "value" 
    :disabled="isPending"
    :color="color"
    @click.stop.prevent="handleClick"
  >
    <p 
      v-if="isPending"
    >o
    </p>
    <slot />
  </base-button>
</template>

<script>
import BaseButton from './BaseButton.vue'

export default {
  name: 'AsyncButton',
  components: { BaseButton },
  inheritAttrs: false,

  props: {
    value : String,
    color: {
      type: String,
      default: 'primary'
    },
  },
  
  data () {
    return {
      time : 0,
      isPending: false
    }
  },
  
  methods: {
    handleClick () {
      this.time += 1000
      const originalOnClick =  new Promise(resolve => setTimeout(resolve, this.time))
      this.isPending = true
      originalOnClick.finally(() => { this.isPending = false })
    }
  }
}
</script>