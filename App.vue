<template>
  <div id="app" class="app">
    <div class="container">
      <img alt="" src=""/>
    </div>
  </div>
</template>

<script>

  export default {
  }
</script>

<style>
  html, body, #app {
    width: 100%;
    height: 100%;
  }
  .app {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .container {
    width: 450px;
    height: 450px;
    background-color: #eee;
    box-shadow: 0 2.5rem 5rem rgba(0, 0, 0, .45);
  }
  img {
    width: 100%;
    height: 100%;
    border: 0;
  }


  @media (max-width: 768px) {
    .container {
      width: 320px;
      height: 320px;
    }
  }

  @media (max-width: 500px) {
    .container {
      width: 250px;
      height: 250px;
    }
  }
</style>
