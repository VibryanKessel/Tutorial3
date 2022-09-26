<template>
    <button :class = "(disabled)? 'btn-disabled' : 'btn-hover' ">{{ value }}</button>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
    name : 'BaseButton',
    props: {
        value : String,
        disabled : Boolean,
    }    
})
</script>

<style scoped>
    button{
        background-color: rgba(0,150,0,.8);
        color : white;
        padding: 25px 100px;
        border: 0;
        border-radius: 2%;
        font-weight: bold;
        font-size: 15px;
        transition: 1s;
    }
    .btn-disabled{
        background-color: rgba(0,150,0,.5);    
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
</style>