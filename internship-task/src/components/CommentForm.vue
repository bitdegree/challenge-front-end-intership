<template>
    <div class="commentForm">
        <form @submit="addComment">
            <div class="commentForm-inputs">
    
                <input type="text" placeholder="Add your name" name="userName" v-model="userName" required>
               
                <textarea type="text" placeholder="Add a comment" name="userComment" v-model="userComment" required />

            </div>
            <div class="commentForm-buttons">
                <button type="submit" class="btn btn-success">Post</button>
                <button @click="cancelComment" type="button" class="btn btn-secondary">Cancel</button>
            </div>
        </form>
</div>
</template>

<script>
import {v4 as uuidv4 } from 'uuid';

export default {
    name: "CommentForm",
    data() {
        return {
            userName: '',
            userComment: ''
        }
    },
    methods: { 
        addComment(e) {
            e.preventDefault();
            const timeStamp = require('time-stamp');
            const newComment = {
                id: uuidv4(),
                timeStamp: timeStamp('HH:mm'),
                name: this.userName,
                message: this.userComment,
                completed: false
            };
            this.$emit('add-comment', newComment);
            this.userName = '';
            this.userComment = '';
        },
        cancelComment(e){
            e.preventDefault();
            this.userName = '';
            this.userComment = '';
        }
    }
}
</script>


<style scoped>
input, textarea{
    border: none;
    background-color: rgb(240, 240, 240);
    color: rgb(150, 150, 150);
    padding: 5px;
    border-radius: 5px;
}

input{
    font-size: 14px;
}

textarea{
    width: 100%;
    margin: 10px 0;
}

textarea::placeholder {
    font-size: 26px;
}

input:focus::placeholder, textarea:focus::placeholder{
    color: transparent;
}

input:focus, textarea:focus{
    outline: none;
}
.commentForm{
    background-color: rgb(250, 250, 250);
    border-radius: 0 0 10px 10px;
    padding: 20px;
    box-shadow: 2px 5px 3px rgba(0, 0, 0, 0.3);
}

button{
    margin: 3px;
}
</style>