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
  