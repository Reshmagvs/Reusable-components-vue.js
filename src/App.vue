<template>
  <div :class="darkMode ? 'dark-container' : 'light-container'">
    <h1>🚀 Reusable Component in Vue.js</h1>
    <GradientButton label="Click Me" @click="showAlert" />
    <br />
    <button class="theme-button" @click="toggleTheme">
      {{ darkMode ? "☀️ Light Mode" : "🌙 Dark Mode" }}
    </button>
  </div>
</template>

<script>
import GradientButton from "./components/GradientButton.vue";

export default {
  components: { GradientButton },
  data() {
    return {
      darkMode: false,
    };
  },
  methods: {
    toggleTheme() {
      this.darkMode = !this.darkMode;
    },
    showAlert() {
      alert("Clicked!");
    },
  },
};
</script>

<style>
.light-container {
  text-align: center;
  padding: 50px;
  background: linear-gradient(135deg, #f8f9fa, #d6e4f0);
  transition: all 0.5s ease-in-out;
}

.dark-container {
  text-align: center;
  padding: 50px;
  background: linear-gradient(135deg, #1e1e1e, #333);
  color: white;
  transition: all 0.5s ease-in-out;
}

.theme-button {

}
</style>
  margin-top: 20px;
  background: linear-gradient(90deg, #ffcc00, #ff8800);
  color: #333;
  padding: 12px 18px;
  font-size: 18px;
  border-radius: 10px;
  border: none;
  cursor: pointer;
  transition: 0.3s ease-in-out;
  font-weight: bold;
}