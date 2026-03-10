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
  <main class="main">



    <div class="flex">
      <div>
        <h1>Install Minecraft Legacy Console Edition?</h1>
        <button class="app-btn app-btn-primary">
          <i class="icons10-fantasy"></i>
          <span>Primary Button</span>
        </button>
      </div>
      <div>
        <img class="logo" src="/images/table.png" />
      </div>
    </div>


    <div class="flex">
      <input class="app-checkbox" type="checkbox" value="" id="CheckBoxDefault" checked>
      <label for="CheckBoxDefault">Install for all users</label>
    </div>




  </main>
</template>

<style scoped>
.flex {
  display: flex;
}
.logo {
  width: 5rem;
  height: 5rem;
}
</style>

<style>
.main {
  padding: 2rem;
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