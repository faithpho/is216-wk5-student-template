<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])
const newItem = ref("")
// TODO: Add Code Here
function deleteItem(index){
    items.value.splice(index,1)
}

function addItem(){
    items.value.push(newItem.value)
}
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul>
        <li v-for="(item, index) in items">
            {{ item }}
            <button @click="deleteItem(index)">Delete!</button>
        </li>
    </ul>
    <input type="text" v-model="newItem">
    <button @click="addItem(newItem)">Add!</button>
</template>
