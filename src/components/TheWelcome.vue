<template>
  <div class="valentine-container">
    <div class="valentine-card">
      <h1>Для самой прекрасной девушки! 💖</h1>
      <p>Ты делаешь мои дни ярче, как солнце в пасмурный день.</p>
      <p>Спасибо за то, что ты есть, Иви!</p>
      <p>Спасибо, что согреваешь мне душу каждый день!</p>
      <p>Спасибо, что заставляешь меня улыбаться каждый день!</p>
      <p>Ты лучшая, Ивочка!</p>
      <div class="buttons">
        <p>Ты принимаешь валентинку?</p>
        <button class="yes-button" @click="acceptValentine">Да</button>
        <button
          class="no-button"
          @mouseover="moveNoButton"
          :style="noButtonStyle"
        >
          Нет
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const noButtonStyle = ref({
  position: 'absolute',
  left: '50%',
  top: '50%',
});

function moveNoButton() {
  const randomX = Math.random() * window.innerWidth * 0.8; 
  const randomY = Math.random() * window.innerHeight * 0.8; 
  noButtonStyle.value = {
    position: 'absolute',
    left: `${randomX}px`,
    top: `${randomY}px`,
    transition: 'left 0.3s, top 0.3s', 
  };
}

function acceptValentine() {
  alert('Лучшая! Обожаю тебя! 💖');
}
</script>

<style scoped>

html, body {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
  overflow: hidden; 
}
#app {
  height: 100%;
  width: 100%;
}

.valentine-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh; 
  width: 100%;
  height: 100%;
  position: relative;
}

.valentine-container::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 800px; /* Размер */
  height: 800px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%23ff7eb9'%3E%3Cpath d='M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z'/%3E%3C/svg%3E");
  background-size: contain;
  background-repeat: no-repeat;
  opacity: 0.2;
  z-index: 1;
}

.valentine-card {
  text-align: center;
  font-family: 'Comic Sans MS', cursive, sans-serif;
  padding: 20px;
  color: #ff4757;
  position: relative;
  z-index: 2; 
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

p {
  font-size: 1.2rem;
  margin: 10px 0;
}

.buttons {
  margin-top: 20px;
  position: relative;
}

button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
  margin: 0 10px;
}

.yes-button {
  background: #4caf50;
  color: white;
}

.yes-button:hover {
  background: #45a049;
}

.no-button {
  background: #ff4757;
  color: white;
}

.no-button:hover {
  background: #ff6b81;
}
</style>
