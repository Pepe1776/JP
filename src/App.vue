<script setup lang="ts">
import { ref } from 'vue';
const show = ref(true);
</script>

<template>
  <nav>
    <router-link to="/">
      <img class="brand" src="./assets/jjp2.png" alt="logo">
    </router-link>
  </nav>
  <main>
    <Transition name="slide-fade">
      <img v-if="show" src="./assets/011.jpeg" class="main-img" alt="logo" />
    </Transition>
   <button class="enter-btn" @click="show = !show">Enter</button>
  </main>
</template>

<style>
#app {
 box-sizing: border-box;
 margin: 0;
 padding: 0;
 font-family: sans-serif;
}
main {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-left: -20px;;
}
.main-img {
 position: absolute;
 width: 50%;
 height: auto;
 left: 50%;
 top: 50%;
 transform: translate(-50%, -50%);
 opacity: 0.3;
}
.brand {
  position: absolute;
  width: 100px;
  height: auto;
  left: 3%;
  top: 3%;
  opacity: 0.9;
  cursor: pointer;
}
.enter-btn {
  width: 100px;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0.9;
  cursor: pointer;
  font-size: 10rem;
  font-weight: bold;
  color: #fff;
  background-color: transparent;
  border: none;
  text-shadow: rgb(0, 0, 0) 10px 10px 15px,rgb(0, 255, 140) 10px 10px 25px;
  border-radius: 5%;
  font-family: 'sarah script', cursive;
  width: 200px;
  transform: scale(1);
  animation: pulse-black 2s infinite;
}
@keyframes pulse-black {
  0% {
    transform: scale(0.95);
    box-shadow: 0 0 0 0 rgb(255, 255, 255);
  }

  70% {
    transform: scale(1);
    box-shadow: 0 0 0 10px rgba(0, 0, 0, 0);
  }

  100% {
    transform: scale(0.95);
    box-shadow: 0 0 0 0 rgba(0, 0, 0, 0);
  }
}
@keyframes myAnim {
  0% {
    background-position: center top;
    background-size: 100%;
  }

  100% {
    background-position: center top;
    background-size: 150%;
  }
}
/*
  Enter and leave animations can use different
  durations and timing functions.
*/
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}
</style>
