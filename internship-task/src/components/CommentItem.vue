<template>
    <div class="comment">
        <div class="avatar">
            {{getFirstLetter()}}
        </div>
        <div class="commentText" >
            <div class="commentHeader" >
                <span class="name" >{{ comment.name }}</span>
                <span class="timeStamp" >{{ comment.timeStamp }}</span>
                <i class="fa fa-minus-square" @click="$emit('remove-comment', comment.id)"></i>
            </div>
            <p class="message" >{{ comment.message }}</p>

        </div>
    </div>
</template>

<script>
export default {
    name: "CommentItem",
    props: ["comment"],

    methods: {
        getFirstLetter() {
            const firstLetter = this.comment.name.split('');
            return firstLetter[0];
        }
    }
}
</script>



<style scoped>
    .comment{
        display: flex;
        margin: 10px;
        padding: 5px;
        width: 100%;
    }

    .commentText{
        width: 100%;
    }

    .avatar{
        margin: 0 10px;
        min-width: 50px;
        max-height: 50px;
        border-radius: 25px;
        background-color: rgb(5, 5, 5);
        color: rgb(235, 235, 235);
        text-align: center;
        font-size: 30px;
        
    }

    .name{
        margin-right: 5px;
        font-size: 18px;
    }

    .timeStamp{
        font-size: 14px;
        color: rgb(150, 150, 150)
    }

    .fa-minus-square{
        float:right;
        opacity: 0;
        color: red;
    }

    .comment:hover .fa-minus-square{
        opacity: 1;
        cursor: pointer;
        transition: 1s ease;
        
    }

    .message{
        width: 100%;
    }
</style>