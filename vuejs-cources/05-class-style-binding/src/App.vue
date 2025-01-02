<script setup>
import { ref,reactive, computed} from 'vue'

const styleObject = reactive({
    color: 'red',
    fontSize: '13px'
})

</script>

<template>
    <div>
        <button :style=[styleObject]>Active</button>
    </div>

</template>

<style>
.active{
    border: none;
    background: #f1f1f1;
    color: #000;
    padding: 10px 14px;
    border-radius: 6px;
    cursor: pointer;
    &:hover{
        background: #ddd;
    }

}
</style>
