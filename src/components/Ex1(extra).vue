<script setup>

import { ref } from 'vue';

const id = ref("shape")
const clss = ref('circle')

function mOver() {
    // add code here
    clss.value = 'square'
}

function mOut() {
    // add code here
   clss.value = 'circle'
}
</script>

<template>
    <!-- modify code below -->
     <!-- v-bind:id = "id" same as :i"id-->
    <div :id="id" :class="clss" @mouseover="mOver" @mouseout="mOut">
        Mouse Over Me
    </div>

</template>

<style scoped>
#shape {
    width: 150px;
    height: 150px;
    background-color: goldenrod;
    text-align: center;
    padding-top: 60px;
}

.circle {
    border-radius: 50%;
}
.square {
    border-radius: 0%;
}
</style>
