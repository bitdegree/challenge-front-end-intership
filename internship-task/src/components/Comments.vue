<template>
    <div class="background">
        <div v-if="this.test() > 0">
            <p class="earlierComments" @click="limit += 20">{{this.test()}} earlier comments</p>
        </div>

        <div v-if="comments.length > 0">
            <transition-group name="test" enter-active-class="animated zoomIn" leave-active-class="animated zoomOut">
                <div v-bind:key="comment.id" v-for="comment in limitedComments" >
                    <CommentItem  v-if="show" v-bind:comment="comment" v-on:remove-comment="$emit('remove-comment', comment.id)" />
                </div>
            </transition-group>
        </div>

        <div v-else>
            <h3>No comments...</h3>
        </div>

    </div>
</template>

<script>
import CommentItem from './CommentItem';

export default {
    name: "Comments",
    props: ["comments"],
    components: {
        CommentItem
    },
    data(){
        return{
            limit: 4,
            show: true
        }
    },
    computed: {
        limitedComments() {
            return this.limit ? this.comments.slice(0, this.limit) : this.comments  
        }
    },
    methods: {
        test() {
            const a = this.limitedComments.length;
            const b = this.comments.length;
            const moreComments = b - a;

            return moreComments;
        }, 
    }
}
    
</script>

<style scoped>
   .earlierComments{
       cursor: pointer;
   }
</style>