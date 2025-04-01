# Understanding Reusable components in Vue.js 

Output:

![Alt Text](https://github.com/Reshmagvs/Reusable-components-vue.js/blob/main/reuse_vue.png)

1. Setup a Vue Project in VS Code
````
npm create vue@latest my-vue-app 
cd my-vue-app
npm install
 
````
2. Replace the code in App.vue , which will be in src folder :
```
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
```
3. Add GradientButton.vue file under components folder and write the code :
```
<template>
    <button class="styled-button" @click="$emit('click')">{{ label }}</button>
  </template>
  
  <script>
  export default {
    props: {
      label: String,
    },
  };
  </script>
  
  <style>
  .styled-button {
    background: linear-gradient(90deg, #007BFF, #00C9FF);
    color: white;
    padding: 14px 24px;
    font-size: 18px;
    font-weight: bold;
    border-radius: 12px;
    border: none;
    cursor: pointer;
    transition: 0.4s ease-in-out;
    box-shadow: 4px 4px 15px rgba(0, 0, 0, 0.2);
  }
  
  .styled-button:hover {
    background: linear-gradient(90deg, #0056b3, #0093E9);
    transform: scale(1.08);
    box-shadow: 6px 6px 20px rgba(0, 0, 0, 0.3);
  }
  </style>
  ```
4. Run your vue app
```
npm run dev
```
