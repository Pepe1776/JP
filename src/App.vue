<script setup lang="ts">
import { ref } from 'vue';
const show = ref(true);
const show2 = ref(false);
</script>

<template>
  <nav>

    <img @click="show2 = !show2" class="brand" src="./assets/jjp2.png" alt="logo">

  </nav>
  <main>
    <Transition name="slide-fade">
      <img v-if="show" src="./assets/jjp2.png" class="main-img" alt="logo" />
    </Transition>
    <Transition name="slide-fade">
      <img v-if="show2" src="./assets/011.jpeg" class="main-img2" alt="logo" />
    </Transition>
    <Transition name="slide-fade">
      <img v-if="show2" src="./assets/011.jpeg" class="main-img" alt="logo" />
    </Transition>
    <button v-if="show" class="enter-btn" @click="show = !show">Enter</button>
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
.main-img2 {
 position: absolute;
  width: 100px;
  height: auto;
  left: 3%;
  top: 3%;
  opacity: 0.9;
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
  width: 13%;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0.7;
  cursor: pointer;
  font-size: 10rem;
  font-weight: bold;
  color: #fff;
  background-color: transparent;
  border: none;
  text-shadow: rgb(0, 0, 0) 10px 10px 15px,rgb(0, 255, 140) 10px 10px 25px;
  border-radius: 5%;
  font-family: 'sarah script', cursive;
  transform: scale(1);
  animation: pulse-black 2s infinite;
  transition: all 0.5s ease-in-out;
}
.enter-btn:hover {
 opacity: 1;
}
@media (max-width: 768px) {
  .main-img {
    width: 130%;
  }
  .enter-btn {
    font-size: 6rem;
  }}
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
  transition: all 0.5s ease-out;
}

.slide-fade-leave-active {
  transition: all 1s cubic-bezier(1, 0.9, 0.4, 2);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translate(-150%, -100%) scale(0.3);
  opacity: 0;
}

.fade-slide-enter-active {
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}
.fade-slide-leave-active {
  transition: all 1s cubic-bezier(1, 0.9, 0.4, 2);
}
.fade-slide-enter-active,
.fade-slide-leave-active {
  opacity: 1;
  transform: translate(500%,  -50%) scale(8);
}
</style>
