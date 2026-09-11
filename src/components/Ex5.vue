<script setup>
import axios from 'axios';
import { ref } from 'vue';
const moods = ref(['Happy', 'Sad', 'Angry']);
const subject = ref('');
const entry = ref('');
const mood = ref('');

// Add Code Here
async function submitPost(){
    try {
        const response = await axios.post('http://localhost:8000/posts', {
            subject: subject.value,
            entry: entry.value,
            mood: mood.value
        })
        console.log(response.data)
        // clear the form fields after successful submit
        subject.value = ''
        entry.value = ''
        mood.value = ''
    } catch (error){
        console.log(error.message)
    } 
}

</script>

<template>
    <div class="table m-2">
        <h3>Add a New Blog Post</h3>

        Subject: <input type='text' size='30' v-model='subject' required>
        <br>

        Entry: <br>
        <textarea name='entry' cols='80' rows='5' v-model='entry' required></textarea>
        <br>

        Mood:
        <!-- TODO: Build a dropdown list here for selecting the mood -->
        <br>

        <select v-model="mood">
            <option v-for="mood in moods" :value="mood">{{ mood }}</option>
        </select>

        <br>
        <button @click="submitPost">Submit New Post</button>

        <hr>
        <RouterLink to="/ViewPosts/">Click  here to return to Main Page</RouterLink>  
       
    </div>
</template>

