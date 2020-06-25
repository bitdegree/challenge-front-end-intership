<template>
  <div id="app">
    <CommentBox />
  </div>
</template>

<script>
import CommentBox from './components/CommentBox';

export default {
  name: 'App',
  components: {
    CommentBox
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,600;1,400&display=swap');
@import "https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css";


  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: 'Open Sans', sans-serif;
  }

  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
    display: flex;
    justify-content: center;
  }

</style>
