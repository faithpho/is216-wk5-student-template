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
    newItem.value = ""
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
    <!-- this way either pressing "add!" button or enter will submit cart-->
    <input type="text" v-model="newItem" @keyup.enter="addItem()"> 
    <button @click="addItem(newItem)">Add!</button>
</template>
