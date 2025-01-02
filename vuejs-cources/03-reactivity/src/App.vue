<script setup>
import { ref } from "vue";

const object = ref({
    count:2 ,
    user:{
        age: 18,
    },
    array : [1,2,3,4,5]
})

const change = () => {
    object.value.count += 1
    object.value.user.age += 1
    object.value.array.push(6)
}
</script>

<template>
    <div>
        <p>Count: {{ object.count }}</p>
        <p>Age: {{ object.user.age }}</p>
        <p>Array: {{ object.array }}</p>
=        <button @click="change">Incrase</button>
    </div>
  
</template>
