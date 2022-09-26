<template>
  <button
    :color="color"
    :class="[disabled ? 'btn-disabled' : 'btn-hover', color]"
  >
    {{ value }}
  </button>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "BaseButton",
  props: {
    value: String,
    disabled: Boolean,
    color: {
      default: "primary",
      type: String,
    },
  },
  watch: {
    color: function (value) {
      switch (value) {
        case "warn":
          return "warn";
        case "danger": 
          return  "danger";
        default: "primary";
    }
}
    } 
})
</script>

<style scoped>
    button{
        color: white;
        padding: 25px 100px;
        border: 0;
        border-radius: 2%;
        font-weight: bold;
        font-size: 15px;
        transition: 1s;
    }
    .btn-disabled{
        opacity: .5;    
    }
    .btn-disabled:hover{
        cursor: not-allowed;
    }
    .btn-hover:hover{
        background-color: white;
        color: black;
        border: 2px solid;
        cursor: pointer;
        transition: 1s;
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }
    .primary{
        background-color: rgba(0,150,0,.8);
    }
    .warn{
        background-color: rgba(190, 80, 0, 0.8);
    }
    .danger{
        background-color: rgba(190, 0, 0, 0.8);
    }
</style>