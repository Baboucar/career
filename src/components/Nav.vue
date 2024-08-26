<template>
    <div class="main">
      <div class="header">
        <div class="logo">Logo</div>
        <div class="hamburger" @click="toggleMenu">&#9776;</div>
      </div>
      <div class="nav" :class="{ visible: isMenuVisible || isWideScreen }">
        <router-link to="/">Home</router-link>
        <router-link to="/">About Us</router-link>
        <router-link to="/">Gallery</router-link>
        <router-link to="/">Services</router-link>
        <router-link to="/">Contacts</router-link>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isMenuVisible: false,
        isWideScreen: false,
      };
    },
    methods: {
      toggleMenu() {
        this.isMenuVisible = !this.isMenuVisible;
      },
      checkScreenWidth() {
        this.isWideScreen = window.innerWidth >= 1024; // 64rem = 1024px
      },
    },
    mounted() {
      this.checkScreenWidth();
      window.addEventListener("resize", this.checkScreenWidth);
    },
    beforeDestroy() {
      window.removeEventListener("resize", this.checkScreenWidth);
    },
  };
  </script>
  
  <style lang="scss" scoped>
  .header {
    display: flex;
    background: #1f252f;
    padding: 1rem;
  }
  .logo {
    margin-right: auto;
    font-size: 1.2rem;
    color: #ffffff;
  }
  .hamburger {
    font-size: 1.5rem;
    color: #ff033d;
    font-weight: bold;
    cursor: pointer;
  }
  
  .nav {
    background: #f4f4f4;
    display: none;
  
    &.visible {
      display: block;
    }
  }
  
  a {
    display: block;
    text-align: center;
    padding-top: 0.5rem;
    color: #000000;
  }
  
  @media (min-width: 64rem) {
    .hamburger {
      display: none;
    }
    
    .nav {
      display: block !important;
      margin-left: 25rem;
      background: #1f252f;
 
    }
    .main{
        display: flex;
        background: #1f252f;
    }
    a{
        display: inline-block;
        padding-left: 2rem;
        color: #ffffff;
        margin-top: 0.5rem;


    }
    .logo{ 
        padding-left: 12rem;
    }
  }
  </style>
  