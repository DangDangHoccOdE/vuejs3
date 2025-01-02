<script setup>
import { reactive, computed } from "vue";

const book = reactive({
    name: "Book 1",
    chaper: []
})

const addChaper = () => {
    book.chaper.push(`Chaper`)
}

const isPublished = computed(() => {
    return book.chaper.length > 0 ? "Yes" : "No"
})

</script>

<template>
    <div>
        <p id="count">Book name: {{ book.name }}</p>
        <p id="count">Đã xuất bản: {{ isPublished }}</p>
=        <button @click="addChaper">Add Chaper</button>
    </div>
  
</template>
