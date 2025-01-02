<script setup>
const message = 'Hello'
const rawHtml = '<span style="color: red">This should be red.</span>'
const buttonId = 'button-id'
const buttonClass = 'btn btn-primary'
const objectOfAttributes = {
    id: 'container',
    class: 'wrapper',
}
const number = 0
const convertToId = (data) => 
    data.split(',').reverse().join('-')

const listString = 'a,b,c,d,e,f,g,h,i,j'
const attribute = 'href'
const url = "https://www.google.com"
</script>

<template>
    <h1>Systax</h1>
    <h2>{{ message }}</h2>
    <span v-html="rawHtml"></span>
    <button :id="buttonId" :class="buttonClass ">Click here</button>
    <button v-bind="objectOfAttributes">Click here2</button>
    <button>Number: {{ number }}</button>
    <button :id="convertToId(listString)">Click here 4</button>
    <a v-bind:[attribute]="url">Google</a>
</template>
