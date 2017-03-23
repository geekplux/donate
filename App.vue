<template>
  <div id="app" class="app">
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
    <div class="image">
      <div class="img-wrap">
        <div class="blur"></div>
        <img alt="" :src="img"/>
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
    align-items: center;
  }

  .image {
    width: 70%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .img-wrap {
    position: relative;
    width: 450px;
    height: 450px;
    box-shadow: 0 2.5rem 5rem rgba(0, 0, 0, .45);
  }
  img {
    width: 100%;
    height: 100%;
    border: 0;
  }

  .blur {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.35);
  }

  .content {
    width: 30%;
    padding-left: 100px;
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
    margin-bottom: 80px;
  }

  button {
    margin: auto 0 0 0;
    border: 3px solid #000;
    background-color: transparent;
    color: #000;
    padding: 8px 40px;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 18px;
    font-weight: bold;
    outline: none;
    cursor: pointer;
    transition: .5s;
  }
  button:hover {
    background-color: #000;
    color: #fff;
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
    color: #000;
    font-weight: lighter;
    text-decoration: none;
  }

  hr {
    height: 1px;
    border: 0;
    background-image: -webkit-linear-gradient(0deg, #888, #888, #eee);
  }
</style>
