<template>
  <div class="quote-container">
    <blockquote class="note yellow">
      I can do anything once I've had a cup of SleepyTime Tea, perhaps even fall sleep.
      <cite class="author">Dillon Brady</cite>
    </blockquote>
  </div>
</template>

<style lang="css">
  @import url(https://fonts.googleapis.com/css?family=Satisfy);

  .quote-container {
    margin-top: 50px;
    position: relative;
  }
  
  .note {
    color: #333;
    position: relative;
    width: 500px;
    height: 500px;
    margin: 0 auto;
    padding: 20px;
    font-family: Satisfy;
    font-size: 30px;
    box-shadow: 0 10px 10px 2px rgba(0,0,0,0.3);
  }
  .note .author {
    display: block;
    margin: 40px 0 0 0;
    text-align: right;
  }

  .yellow {
    background: #eae672;
    -webkit-transform: rotate(2deg);
    -moz-transform: rotate(2deg);
    -o-transform: rotate(2deg);
    -ms-transform: rotate(2deg);
    transform: rotate(2deg);
  }

</style>