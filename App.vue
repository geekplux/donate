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
    <div class="qrcode-imgs">
      <div class="parallax">
        <div class="parallax-top-left parallax-dir"></div>
        <div class="parallax-top-right parallax-dir"></div>
        <div class="parallax-bottom-left parallax-dir"></div>
        <div class="parallax-bottom-right parallax-dir"></div>
        <div class="parallax-content">
          <div class="blur" :class="[ paypal ? 'blur-35' : 'blur-10' ]"></div>
          <div class="parallax-front">
            <h2>Alipay</h2>
          </div>
          <div class="parallax-back">
            <img class="back-img" alt="" :src="img"/>
          </div>
        </div>
      </div>
      <div class="parallax">
        <div class="parallax-top-left parallax-dir"></div>
        <div class="parallax-top-right parallax-dir"></div>
        <div class="parallax-bottom-left parallax-dir"></div>
        <div class="parallax-bottom-right parallax-dir"></div>
        <div class="parallax-content">
          <div class="blur" :class="[ paypal ? 'blur-35' : 'blur-10' ]"></div>
          <div class="parallax-front">
            <h2>WeChat</h2>
          </div>
          <div class="parallax-back">
            <img class="back-img" alt="" :src="img"/>
          </div>
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
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .qrcode-imgs {
    display: flex;
  }

  .back-img {
    display: block;
    width: 40vmin;
    height: 40vmin;
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
    width: 70%;
    text-align: left;
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
    color: #000;
    font-weight: lighter;
    text-decoration: none;
  }

  hr {
    height: 1px;
    border: 0;
    background-image: -webkit-linear-gradient(0deg, #000, #aaa, #fff);
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



  .parallax {
    display: block;
    height: auto;
    position: relative;
    width: auto;
  }
  .parallax:first-child {
    margin-right: 10vw;
  }


  .parallax-content {
    height: auto;
    transform: perspective(100rem);
    transform-style: preserve-3d;
    transition: all .4s ease;
    width: 100%;
    box-shadow: 0 2.5rem 5rem rgba(0, 0, 0, .45);
  }
  .parallax-content:before {
    content: "";
    display: block;
    height: 100%;
    left: 0;
    position: absolute;
    top: 0;
    width: 100%;
  }


  .parallax-front {
    align-items: center;
    color: #fff;
    display: flex;
    height: 100%;
    justify-content: center;
    left: 0;
    position: absolute;
    text-align: center;
    top: 0;
    transform: translateZ(10rem);
    transition: all .4s ease;
    width: 100%;
    z-index: 0;
  }

  .parallax-top-left {
    left: 0;
    top: 0;
  }
  .parallax-top-left:hover ~ .parallax-content {
    transform: perspective(100rem) rotateX(-3deg) rotateY(3deg);
  }
  .parallax-top-left:hover ~ .parallax-content:before {
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.25) 0%, rgba(255, 255, 255, 0) 50%);
  }
  .parallax-top-left:hover ~ .parallax-content .parallax-front {
    transform: translate3d(-0.65rem, -0.65rem, 10rem);
  }


  .parallax-top-right {
    right: 0;
    top: 0;
  }
  .parallax-top-right:hover ~ .parallax-content {
    transform: perspective(100rem) rotateX(-3deg) rotateY(-3deg);
  }
  .parallax-top-right:hover ~ .parallax-content:before {
    background: linear-gradient(-135deg, rgba(255, 255, 255, 0.25) 0%, rgba(255, 255, 255, 0) 50%);
  }
  .parallax-top-right:hover ~ .parallax-content .parallax-front {
    transform: translate3d(0.65rem, -0.65rem, 10rem);
  }


  .parallax-bottom-left {
    bottom: 0;
    left: 0;
  }
  .parallax-bottom-left:hover ~ .parallax-content {
    transform: perspective(100rem) rotateX(3deg) rotateY(3deg);
  }
  .parallax-bottom-left:hover ~ .parallax-content:before {
    background: linear-gradient(45deg, rgba(255, 255, 255, 0.25) 0%, rgba(255, 255, 255, 0) 50%);
  }
  .parallax-bottom-left:hover ~ .parallax-content .parallax-front {
    transform: translate3d(-0.65rem, 0.65rem, 10rem);
  }



  .parallax-bottom-right {
    bottom: 0;
    right: 0;
  }
  .parallax-bottom-right:hover ~ .parallax-content {
    transform: perspective(100rem) rotateX(3deg) rotateY(-3deg);
  }
  .parallax-bottom-right:hover ~ .parallax-content:before {
    background: linear-gradient(-45deg, rgba(255, 255, 255, 0.25) 0%, rgba(255, 255, 255, 0) 50%);
  }
  .parallax-bottom-right:hover ~ .parallax-content .parallax-front {
    transform: translate3d(0.65rem, 0.65rem, 10rem);
  }



  .parallax-dir {
    height: 50%;
    position: absolute;
    width: 50%;
    z-index: 1;
  }
</style>
