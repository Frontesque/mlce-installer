<script setup>
import { ref } from "vue";
import { invoke } from "@tauri-apps/api/core";

const greetMsg = ref("");
const name = ref("");

async function greet() {
  // Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
  greetMsg.value = await invoke("greet", { name: name.value });
}
</script>

<template>
  <main class="container">



    <h1>Welcome to Tauri + Vue</h1>

    <button class="app-btn app-btn-primary">
  <i class="icons10-fantasy"></i>
  <span>Primary Button</span>
</button>
<button class="app-btn" @click="toggle_theme()">
  <span>Default Button</span>
</button>



  </main>
</template>

<style>
* {
  font-family: ;
}
</style>

<script>
export default {
  methods: {
    toggle_theme() {
      const colorScheme = Appearance.getColorScheme();
      if (colorScheme === "dark") {
        Appearance.setLightScheme()
      } else {
        Appearance.setDarkScheme();
      }
    }
  }
}
</script>