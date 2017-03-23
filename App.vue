<template>
  <div id="app" class="app">
    <div class="content">
        <h1>Donation</h1>
        <p>
          if you enjoy my works, you could donate to me. It’s the best rewards and I’ll use these money to learn more. Thank you.
        </p>
        <div class="buttons">
          <button @click="alipayClick">Alipay</button>
          <button @click="wechatClick">WeChat</button>
          <button @click="paypalClick">PayPal</button>
        </div>
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
        <div class="blur" :class="[ paypal ? 'blur-35' : 'blur-10' ]"></div>
        <img alt="" :src="img"/>
        <div v-if="paypal" class="paypal">
          <h3>PayPal</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import desktop from './images/desktop.jpg'
  import alipayQR from './images/alipayQR.jpg'
  import wechatQR from './images/wechatQR.jpg'

  export default {
    name: 'app',
    data() {
      return {
        img: desktop
      }
    },
    computed: {
      paypal() {
        return this.img === desktop
      }
    },
    methods: {
      paypalClick() {
        this.img = desktop
        window.open('https://www.paypal.me/geekplux')
      },
      alipayClick() {
        this.img = alipayQR
      },
      wechatClick() {
        this.img = wechatQR
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
    min-width: 1000px;
    overflow-x: scroll;
  }

  .image {
    width: 70%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .image:hover .img-wrap {
    transform-style: preserve-3d;
    transform: perspective(600px) rotateY(-5deg);
  }

  .img-wrap {
    position: relative;
    width: 450px;
    height: 450px;
    box-shadow: 0 2.5rem 5rem rgba(0, 0, 0, .45);
    transition: .5s;
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
  }
  .blur-35 {
    background: rgba(0, 0, 0, 0.35);
  }
  .blur-10 {
    background: rgba(0, 0, 0, 0.1);
  }

  .content {
    width: 30%;
    padding-left: 100px;
  }

  h1, h3 {
    font-family: Impact, Charcoal, sans-serif;
    font-size: 40px;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  p {
    font-weight: lighter;
    font-size: 16px;
    margin-bottom: 60px;
  }

  .buttons {
    display: flex;
    border: 3px solid #000;
    border-right: 0;
    margin-bottom: 40px;
  }

  button {
    flex: 1;
    border: 0;
    box-sizing: border-box;
    border-right: 3px solid #000;
    margin: 0;
    padding: 10px 20px;
    background-color: transparent;
    color: #000;
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

  .paypal {
    position: absolute;
    top: 50%;
    color: #fff;
    text-align: center;
    width: 100%;
    margin: 0 auto;
    transform: translateY(-50%);
  }
</style>
