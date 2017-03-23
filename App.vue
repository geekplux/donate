<template>
  <div id="app" class="app">
    <div class="container">
      <div class="blur"></div>
      <img alt="" :src="img"/>
      <div class="content">
        <h1>Donation</h1>
        <p>
          if you enjoy my works, you could donate to me. It’s the best rewards and I’ll use these money to learn more. Thank you.
        </p>
        <button>donate</button>
        <ul class="links">
          <hr/>
          <li><a href="http://geekplux.com/archives">Blog</a></li>
          <li><a href="http://geekplux.com/wiki">Wiki</a></li>
          <li><a href="https://github.com/geekplux">GitHub</a></li>
          <li><a href="https://www.instagram.com/geekplux">Instagram</a></li>
          <li><a href="https://twitter.com/geekplux">Twitter</a></li>
          <li><a href="http://geekplux.com/about">About</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  import desktop from './images/desktop.jpg'

  export default {
    name: 'app',
    data() {
      return {
        img: desktop
      }
    }
  }
</script>

<style>
  html, body, #app {
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
  }

  .app {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .container {
    position: relative;
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

  .blur,
  .content {
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
  }

  .blur {
    background: rgba(0, 0, 0, 0.55);
  }

  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    color: #fff;
    padding: 30px;
    text-align: center;
  }

  h1 {
    font-family: Impact, Charcoal, sans-serif;
    font-size: 40px;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  p {
    width: 80%;
    font-weight: lighter;
    font-size: 16px;
  }

  button {
    margin: auto 0 0 0;
    border: 3px solid #fff;
    background-color: transparent;
    color: #fff;
    padding: 8px 40px;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 18px;
    font-weight: bold;
    outline: none;
    cursor: pointer;
    transition: .5s;
  }
  button:hover {
    background-color: #fff;
    color: #000;
  }

  ul {
    padding: 0;
  }
  li {
    list-style: none;
    display: inline-block;
    margin: 0 5px;
  }
  li a {
    color: #fff;
    font-weight: lighter;
    text-decoration: none;
  }

  hr {
    height: 1px;
    border: 0;
    background-image: -webkit-linear-gradient(0deg, #888, #eee, #888);
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
