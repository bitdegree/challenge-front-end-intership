<template>
<div>
    <div class="commentBox">
        <Comments v-bind:comments="commentPost" v-on:remove-comment="removeComment" />
    </div>
    <CommentForm v-on:add-comment="addComment" />
</div>
  
</template>

<script>
import Comments from './Comments';
import CommentForm from './CommentForm';

export default {
    name: "CommentBox",
    props: ["comments"],
    components: {
        Comments,
        CommentForm
    },
    data() {
    return {
      commentPost: [
        {
          id: 1,
          timeStamp: "13:21",
          name: "Kat Stevens",
          message: "George Washington died in 1799. The firs dinosour fossil was discovered in 1824. George Washington never knew dinosours existed.",
        },

        {
          
          id: 2,
          timeStamp: "15:37",
          name: "John Doe",
          message: "You can usually tell a person's tech proficiency by how they phrase their Google searches",
        },

        {
          id: 3,
          timeStamp: "16:20",
          name: "Andrew Smith",
          message: "Going to sleep when you're not feeling well is like turning your body off and back on again to see if it fixes the problem",
        },
      ],
    }
  },
  mounted() {
      if(localStorage.commentPost) {
          this.commentPost = JSON.parse(localStorage.commentPost);
      }
  },
  watch: {
      commentPost(addedComment) {
          localStorage.commentPost =  JSON.stringify(addedComment);
      }
  },

  methods: {
      addComment(newComment) {
          this.commentPost.unshift(newComment)
      },
      removeComment(id) {
          this.commentPost = this.commentPost.filter(comment => comment.id !== id);
      }
  }
}
    

</script>

<style scoped>

.commentBox{
    background-color: rgb(235, 235, 235);
    padding: 20px;
    border-radius: 10px 10px 0 0;
    width: 600px;
    box-shadow: 2px 5px 3px rgba(0, 0, 0, 0.3);
    margin-top: 4em;
}

    
</style>